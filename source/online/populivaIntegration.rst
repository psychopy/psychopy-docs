.. include:: ../global.rst

.. _populivaIntegration:

Recruiting with Populiva
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

`Populiva <https://populiva.com>`_ is a participant recruitment service for online research.

Connecting Populiva to PsychoPy is a matter of telling Populiva the URL for your study and then telling PsychoPy the URLs to use when the participant completes the study or leaves it early.

Example link to provide **to Populiva** as your study link (you will need to replace `myUserName` and `myStudyName`)::

    https://run.pavlovia.org/myUserName/myStudyName/

Example link to provide **to PsychoPy** as your completion URL (copy the exact address for your study from Populiva)::

    https://populiva.com/c/STUDY_ID?code=COMPLETION_CODE

See also `Populiva's PsychoPy guide <https://populiva.com/guides/psychopy>`_.


Setting the study link in Populiva
----------------------------------------

When creating a study on Populiva, enter the URL of your Pavlovia study as the study link. The link must use `https`.

When a participant starts the study, Populiva opens the study link with three parameters added to the URL `query string`_:

- `PARTICIPANT_ID`: a pseudonymous ID for the participant. It stays the same for a participant across your lab's studies, and is different for each lab.
- `STUDY_ID`: the ID of the Populiva study.
- `SESSION_ID`: a new ID for each attempt at the study.

Online, PsychoPy adds URL parameters to `expInfo`, so these values are stored with your data without further changes.

If you would like the values stored under other names, such as `participant` and `session` (the default names for these in PsychoPy), you can add placeholders to the study link. Populiva replaces `{{PARTICIPANT_ID}}`, `{{STUDY_ID}}` and `{{SESSION_ID}}` anywhere in the query string with the values. For example::

    https://run.pavlovia.org/myUserName/myStudyName/?participant={{PARTICIPANT_ID}}&session={{SESSION_ID}}

The three parameters are always added under their own names as well.

Setting the completion URL in PsychoPy
----------------------------------------

On the study page in Populiva, the *Connect your survey* section shows the completion URL for your study. Copy it and paste it into the `Completed URL` field in the Online tab of your PsychoPy :ref:`Experiment Settings <expSettings>`. Participants are sent to this URL when they finish the experiment.

A study can have more than one completion code, and each code can have a different outcome (for example, approving the submission or recording a paid screen-out). The default code sends the submission to manual review. The `Incomplete URL` field is used if the participant exits the task early (e.g. by pressing the escape key); you can set it to the URL for a screen-out code.

Optional quality script
----------------------------------------

Populiva provides an optional script that sends activity counts (such as time on page and tab switches) for a session to Populiva. It does not send responses. If you use it, mention it in your consent form. See `Populiva's PsychoPy guide <https://populiva.com/guides/psychopy>`__ for details.
