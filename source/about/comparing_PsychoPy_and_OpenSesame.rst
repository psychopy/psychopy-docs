.. include:: /price_defs.rst

.. _psychopyVersusPsychtoolbox:

Comparing PsychoPy with Open Sesame
=====================================

PsychoPy and Open Sesame are both python based. In fact, Open Sesame uses PsychoPy as one of its “backend” options and the Open Sesame documentation recommends the PsychoPy backend if good timing is required, but this is still _not_ as good as PsychoPy itself, as explained below. 

Both applications provide a graphical user interface, where you can add code snippets if you wish. PsychoPy provides the option to view the code that the Builder interface generates and to write experiments by hand using Python using the “Coder” interface, if desired, neither of which are possible in Open Sesame.

Flexible dynamic parameters
----------------------------

PsychoPy and Open Sesame differ in their focus for the user, PsychoPy is very temporal in nature (everything follows a time line or “flow”) whereas in Open Sesame the user visualises their experiment more spatially similar to a set of slides. 

Because of the temporal focus of the PsychoPy builder interface, it is very easy to manipulate stimulus attributes frame-by-frame via drop-down with no code needed. You can simply set almost any parameter to update “on every frame”. In Open Sesame, setting stimuli to be dynamic is not built-in but requires the addition of a “coroutines” plugin and has a more limited range of uses.

Lab-based studies
------------------

Both PsychoPy and Open Sesame were designed firstly for in-lab studies and can therefore interact with a range of hardware including EEG, fMRI and eye tracking devices.

Timing
------

PsychoPy has the more precise timing, as can be seen in the `Timing Megastudy (Bridges et al, 2020)`_. Although Open Sesame is using the PsychoPy library as its recommended backend, it uses outdated functions within that library that have been superseded for timing reasons. As a result the keyboard timing and audio stimulus presentation, in particular, have notably poorer performance than PsychoPy itself and that can be seen in the above measurements.

PsychoPy is also unique in providing `Timing Validator`_ components to allow easy checking of stimulus timing during experiment execution, on relatively cheap hardware such as the Cedrus Riponda button box. This means that, even if your operating system or monitor causes timing issues that the software cannot know about, these can be automatically detected by the PsychoPy using the validator hardware.

Surveys
------------------

It is possible to present survey-style questions in Open Sesame, much like you would in PsychoPy, through presenting text and different response types (e.g. rating scales and sliders). 

PsychoPy has the added benefit of Pavlovia surveys which run on survey.js. You can create a survey using Pavlovia survey creator in browser (no need to install software) and you can even import a Qualtrics .qsf file. This is not possible with Open Sesame. 

Pricing
------------------

Both PsychoPy and Open Sesame are free for building and running studies. For in-lab studies they won't cost you anything. 

If you want to run a study online then PsychoPy offers a hosting service, pavlovia.org (costing |price.university.credit| per respondent or |price.university.licenceonly| for an unlimited institutional licence). Open Sesame has the option of JATOS or MindProbe servers, which are free but don't offer the security certification that Pavlovia does. Both PsychoPy and Open Sesame offer paid consultancy support for users needing help creating their experiments. 

Community
------------------

Both platforms also have community user forums and benefit from communities of enthusiastic open-source users. 

PsychoPy has a `larger developer/contributor team <https://github.com/psychopy/psychopy/graphs/contributors?from=18%2F04%2F2026>`__, a larger more active user community, and a proven business model where Open Science Tools is supported by related services (hosting of Pavlovia studies and provision of consultancy services) which is how PsychoPy itself remains free while employing several full-time developers.

Open Sesame has seen much less recent development and is `almost entirely written by Sebastiaan Mathôt <https://github.com/open-cogsci/OpenSesame/graphs/contributors?from=20%2F07%2F2024>`__. It has a “Bus Factor” of roughly “1” as a result, meaning that if Sebastiaan stops work on it he project will likely not be maintained any further. 

Both packages have a user forum. `PsychoPy's forum <https://discourse.psychopy.org/>`__ has over 15,000 members and is very active, with 5-10 posts per day, whereas the `Open Sesame forum <https://forum.cogsci.nl/categories/opensesame>`__ typically has around 5 posts per month.

.. _Timing Megastudy (Bridges et al, 2020): https://peerj.com/articles/9414/
.. _Timing Validator: https://psychopy.org/builder/components/VisualValidatorRoutine.html#visualvalidatorroutine