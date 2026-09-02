.. include:: /price_defs.rst

.. _psychopyVersusGorilla:

Comparing PsychoPy with Gorilla
=====================================

Gorilla is a comparable experiment builder, in some ways, to PsychoPy. It's very easy to use for simple experiments. It has the added convenience that it can be used entirely online without installing any software, but it is less suitable for lab-based studies, especially where millisecond-precise timing, or external hardware, are needed. Gorilla is also considerably more expensive.

PsychoPy provides the option to run the same study locally in the lab using Python, or online using JavaScript. 

Flexible dynamic parameters
---------------------------

PsychoPy allows you to control every aspect of every stimulus. For instance, while Gorilla and PsychoPy both support images as stimuli, in PsychoPy you can rotate, flip, stretch your image, or even set its transparency or contrast, all without writing a line of code. None of those are possible in Gorilla's Image Node settings.

Not only do PsychoPy stimuli support a very rich set of parameters, but these can be updated on every trial or even every screen refresh! That means stimuli can be made to move, resize, bounce, or alter their transparency constantly, making for more dynamic interactive experiments. 

Lab-based studies
-----------------

Because PsychoPy is a Python-based desktop app, you can connect with external devices such as EEG, eye trackers, fMRI and photometers relatively easily (anything possible with Python code can be done in PsychoPy). Because Gorilla is a browser based tool it cannot directly communicate with external devices like serial ports without an additional bridge (e.g. a local application that connects the web browser with the hardware device via websockets).

Conversely PsychoPy can generate either a web-based JavaScript study, which has similar limitations to Gorilla, it can also generate a Python script that runs entirely locally and can easily be connected to devices such as eyetrackers (including Tobii, SR Research, Pupil Labs, EyeLogic devices), brain imaging equipment (such as EEG, fMRI, and fNIRS studies), physiology hardware (such as BIOPAC devices) and calibration devices such as photometers.

The timing of Gorilla (and any web-based experiments, including when you use PsychoPy in web-based studies via Pavlovia) is also less precise. Gorilla staff sometimes claim “millisecond precision” but while most JavaScript packages use a millisecond precise timer that does not equate with millisecond-precise timing. The critical issue is that web-based packages cannot very precisely detect when a screen refresh occurred or when a sound actually reached the speakers. If you measure a reaction time but don't really know when the stimulus started, then it doesn't matter how precise your timer is. For analogy, consider measuring a sprint race with a stopwatch. The stopwatch may have incredible precision, but if you hit the button with your thumb the precision is lost. See the `Timing Megastudy`_ for details of what is actually possible with online and desktop packages.

.. _Timing Megastudy: https://peerj.com/articles/9414/


Surveys
-------

Both PsychoPy and Gorilla have solutions to present surveys and questionnaires online. For PsychoPy the easiest approach is to use a Pavlovia Survey. Both Pavlovia Surveys and Gorillas questionnaire builder support a range of question types including free-text, rating scales, multiple choice grids and rankings. Pavlovia Surveys offer some question types not available in Gorilla Questionnaire builder such as dynamic matrices, signature responses and file uploads. Both platforms offer the option to directly import a .qsf file from Qualtrics. 

For local PsychoPy experiments (not using Pavlovia surveys) there is a form component, but the range of question types here are more limited. You can still use type responses, radio choice options and sliders.

Pricing
-------

PsychoPy is completely free and always will be. That means you can build an experiment, run it on your local machine and gather data at no cost.

If you want to run a study _online_ you can host the study using Pavlovia.org. Pavlovia is a paid-for service, but very low cost (|price.university.credit| per participant or |price.university.licenceonly| for a whole institution with unlimited use). By comparison, with Gorilla you can build your experiment for free, but you can't run it and collect data without credits or a licence (£1.09 per participant or options ranging up to £11,340 for a department licence with unlimited use - see this page for updates on Gorilla's pricing). 

Both Pavlovia and Gorilla teams can provide training via onboarding sessions and private webinars. To buy the unlimited Pavlovia license including private webinars costs £5,200 compared with £20,470 for Gorilla.
