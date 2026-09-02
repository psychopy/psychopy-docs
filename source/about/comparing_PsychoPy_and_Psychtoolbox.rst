.. include:: /price_defs.rst

.. _psychopyVersusPsychtoolbox:

Comparing PsychoPy with Psychtoolbox
=====================================

Both PsychoPy and Psychophysics Toolbox (aka Psychtoolbox, PTB) are open-source software packages used to design and run experiments in neuroscience and psychology. PsychoPy is built on Python and provides a choice of either hand-writing the code (in nicely-formatted Python scripts) or the widely-used graphical "Builder" user interface. That makes it more accessible to users with limited programming experience, and also results in faster, more bug-free experiment creation for experienced programmers. 

Psychtoolbox experiments are created using MATLAB scripts. These are highly susceptible to user error, as the scripts are long and MATLAB is not well-designed for error-free programming methods. Psychtoolbox code is not object-oriented, for instance, and doesn't support named arguments to functions so all function calls contain long lists of arguments that are very hard to read and debug (was size the 3rd or the 4th parameter here?).

Psychtoolbox also depends on the researcher having a MATLAB license (or using Gnu Octave) and now adds its own annual license fee on top, whereas PsychoPy is free, now and always, supported by a financially sustainable business model.

Flexible dynamic parameters
----------------------------

Both PsychoPy and Psychtoolbox provide frame-by-frame control over stimulus attributes. This allows you to change many attributes of a stimulus (position, size, color and more) in a dynamic fashion.

Lab-based studies
------------------

Both PsychoPy and Psychtoolbox were designed firstly for in-lab studies and can therefore interact with a range of hardware including EEG, fMRI and eye tracking.
    
Some people, certainly Mario Kleiner, consider timing precision to be considerably better in Psychtoolbox, but measurements of that using Blackbox Toolkit hardware in the `Timing Megastudy (Bridges et al 2020)`_ found very little difference between them for lab-based studies.

PsychoPy is also unique in providing `Timing Validator`_ components to allow easy checking of stimulus timing during experiment execution, on relatively cheap hardware such as the Cedrus Riponda button box. This means that, even if your operating system or monitor causes timing issues that the software cannot know about, these can be automatically detected by the PsychoPy using the validator hardware.

.. _Timing Megastudy (Bridges et al 2020): https://peerj.com/articles/9414/
.. _Timing Validator: https://psychopy.org/builder/components/VisualValidatorRoutine.html#visualvalidatorroutine

Online studies
------------------

PsychoPy can output its Builder-generated experiments to JavaScript and run them in a web browser. This allows you to run your experiments online, for instance using the Pavlovia.org platform. The timing of experiments in web browsers is never going to be as precise as when they are run locally (despite what some online vendors will tell you), and can't connect with local hardware. Nonetheless online deployment is a useful option for many studies and has other advantages such as a more diverseand automated recruitment.

MATLAB doesn't run in browsers and nobody has made a Psychtoolbox port for JavaScript, so Psychtoolbox isn't suitable for online studies.

Surveys
------------------

At present Psychtoolbox is not commonly used for surveys and questionnaires - it is possible to present survey style questions through presenting text and rating responses for example, but this isn't “out-of-box”. It has no built-in tools like Sliders or Radio buttons, for instance. 

PsychoPy was initially not created for surveys either, but does have a form component to present a range of basic question types in a survey style for local experiments. More recently, PsychoPy can be combined with Pavlovia surveys to present rich surveys and questionnaires online for remote testing. 

Pricing
------------------

PsychoPy is completely free and always will be, that means you can build an experiment, run it on as many local machines as you need and gather data at no cost. Recent releases of Psychtoolbox (3.2.20 or later) require a subscription model of 50 Euros per year for a single user on a single device or 250 Euros per year for 6 machines (This is currently the Early Bird rate advertised as of June 2026 `here <https://www.psychtoolbox.net/>`__). 

Community
------------------

PsychoPy has a larger `developer/contributor team <https://github.com/psychopy/psychopy/graphs/contributors?from=20%2F07%2F2024>`__ and a proven business model where Open Science Tools is supported by related services (hosting of Pavlovia studies and provision of consultancy services) which is how PsychoPy itself remains free despite having professional developer support.

Psychtoolbox is `almost entirely written by Mario Kleiner <https://github.com/kleinerm/Psychtoolbox-3/graphs/contributors?from=20%2F07%2F2024>`__, and therefore has a much lower “Bus Factor” (possibly just “1”). There have been frequent discussions in the vision science community and `calls on the website itself <http://psychtoolbox.org/ActionNeededToSavePsychtoolbox.html>`__ about how to "save" Psychtoolbox.

Both have a user forum (both using Discourse for the purpose) although PsychoPy's forum has over 15,000 members, compared with under 1000 for Psychtoolbox.
