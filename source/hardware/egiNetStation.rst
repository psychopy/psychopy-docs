.. _eginetstation:

Sending events via EGI NetStation
=================================

The `PsychoPy EGI NetStation plugin
<https://pypi.org/project/psychopy-egi-pynetstation/>`_ adds Builder Components,
Device Manager integration, and a Python interface for controlling recordings
and sending ECI event markers to EGI/Magstim NetStation systems. It uses the
`egi-pynetstation <https://egi-pynetstation.readthedocs.io/>`_ network library.

.. note::

   ``psychopy-egi-pynetstation`` is an independent, community-maintained
   project. It is not affiliated with or endorsed by EGI or Magstim EGI.

Requirements and installation
-----------------------------

The plugin requires |PsychoPy| 2026.1 or newer and Python 3.10 or newer. You
also need the IP address of the computer running NetStation, its ECI port
(normally ``55513``), and the amplifier NTP server address.

Install ``psychopy-egi-pynetstation`` from **Tools > Plugin/packages manager**,
or install it into the Python environment that runs |PsychoPy|:

.. code-block:: console

   python -m pip install psychopy-egi-pynetstation

Restart |PsychoPy| after installation. The three EGI Components then appear in
the **EEG** section of the Components panel.

.. figure:: /images/egi-plugin-components.png
   :alt: PsychoPy Builder with the EGI Components shown under EEG
   :width: 100%

   EGI Start Recording, EGI Send Event, and EGI Stop Recording.

Configure NetStation in Device Manager
--------------------------------------

Open **Device Manager**, add **EGI NetStation**, and choose **EGI NetStation
(manual configuration)**. NetStation cannot be auto-discovered; this entry is
an editable profile, not evidence that an amplifier was detected. Give the
device a stable label such as ``netstation``.

.. figure:: /images/egi-plugin-device-add.png
   :alt: Adding an EGI NetStation manual profile in Device Manager
   :width: 65%

On the **Device** tab, replace the example network values with those used by
your acquisition system. ``NTEL`` is the correct endianness for current Intel
and Apple Silicon Macs, Windows, and most ARM64 Linux systems.

.. figure:: /images/egi-plugin-device-network.png
   :alt: EGI NetStation network options in Device Manager
   :width: 75%

The **Drift** tab enables automatic background clock-drift sampling by default.
The optional warmup setting builds a provisional model early in the session;
enable it when timing tests show unstable startup drift.

.. figure:: /images/egi-plugin-device-drift.png
   :alt: EGI NetStation drift options with warmup enabled
   :width: 75%

Device profiles are stored in |PsychoPy|'s per-user ``devices.json`` file, not
in the ``.psyexp`` file. When moving an experiment to another computer or user
account, install the plugin and recreate or import a profile with the same
device label before generating the experiment script.

Build an experiment
-------------------

Add **EGI Start Recording** where recording should begin and select the device
label created above. The plugin connects during Device Manager setup, so a
separate Connect Component is not needed.

.. figure:: /images/egi-plugin-start-recording.png
   :alt: EGI Start Recording selecting the netstation device
   :width: 65%

Add **EGI Send Event** wherever a marker is needed. Event type must contain
exactly four characters, such as ``stim`` or ``resp``. **Event duration (s)**
is the duration stored in NetStation and defaults to ``0.1`` seconds; it is
independent of the ordinary Builder Component stop field.

To synchronize a marker with a visual onset, enter the visual Component's exact
name in **Target visual Component** and place EGI Send Event below that visual
Component in the Routine. The event is queued on the target's first drawing
flip, and network transmission occurs asynchronously so it does not block the
display refresh.

.. figure:: /images/egi-plugin-send-event.png
   :alt: EGI Send Event targeting a visual Component named text
   :width: 65%

.. figure:: /images/egi-plugin-send-event-timeline.png
   :alt: Routine timeline with an EGI event aligned to a visual Component
   :width: 100%

   Put EGI Send Event below its target visual Component in the Routine.

Finally, add **EGI Stop Recording** where recording should end. |PsychoPy|'s
Device Manager also closes the connection during normal or early experiment
shutdown, flushing queued events and reporting send or ECI-response failures.

Use from Coder
--------------

Builder is optional. A code experiment can construct the same wrapper directly:

.. code-block:: python

   from psychopy import visual
   from psychopy_egi_pynetstation import EGINetStation

   win = visual.Window()
   ns = EGINetStation(
       ip="10.10.10.42",
       ntpIP="10.10.10.51",
       port=55513,
       driftWarmup=True,  # optional provisional early-session model
   )

   try:
       ns.connect()
       ns.beginRecording()

       # Capture the event timestamp on the flip that presents the stimulus.
       win.callOnFlip(
           ns.sendEvent,
           eventType="stim",
           label="face",
           duration=0.1,
       )
       win.flip()
   finally:
       ns.close()
       win.close()

For events unrelated to a display refresh, such as a response, call
``ns.sendEvent(...)`` directly. ``ns.close()`` safely stops an active recording,
flushes queued events, reports session health, and disconnects.

Validate before collecting data
-------------------------------

Before a production session:

* confirm that ECI is enabled and both network addresses are reachable;
* send a four-character test marker and inspect it in NetStation;
* use a photodiode or equivalent measurement to validate marker-to-stimulus
  timing on the actual acquisition and display computers;
* inspect the |PsychoPy| log for asynchronous event failures, rejected ECI
  responses, or drift-health warnings; and
* repeat the check after changes to the display, network, operating system, or
  experiment timing.

More information
----------------

See the `plugin documentation
<https://psychopy-egi-pynetstation.readthedocs.io/>`_ for every Builder option,
drift diagnostics, timing guidance, troubleshooting, and the complete Python
API. Source code and issue reporting are available from the
`psychopy-egi-pynetstation GitHub project
<https://github.com/pmolfese/psychopy-egi-pynetstation>`_. For help with the
|PsychoPy| experiment itself, use the
`PsychoPy Forum <https://discourse.psychopy.org/>`_.
