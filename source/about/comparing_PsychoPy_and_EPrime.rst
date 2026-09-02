.. include:: /price_defs.rst

.. _psychopyVersusEPrime:

Comparing PsychoPy with E-Prime
=====================================

If you're looking for an alternative to E-Prime then PsychoPy is an excellent option!

Both applications provide a graphical user interface, where you can add code snippets if you wish, and both will output the entire script for you to view and learn from. E-Prime's script is based on Visual Basic programming language, whereas PsychoPy is built on the more modern Python language.

Both offer millisecond-precise timing and a range of stimuli, although PsychoPy has a slightly wider range and the option for stimulus updates to be every screen refresh.

Another key difference is price. PsychoPy is free and open source, despite having a professional full-time developer team, whereas E-Prime charges $995.00 for a single-user license, and much more if you need hardware plugins.

Flexible dynamic stimulus parameters
------------------------------------

PsychoPy offers a wider range of stimuli: like drifting gratings, “brush” components for drawing inputs, and Random Dot Kinematograms (RDKs), as well as the standard images and movies that E-Prime offers. 

PsychoPy also makes it very easy to manipulate stimulus attributes frame-by-frame within its graphical interface. You can simply set almost any parameter to update “on every frame”. If this is possible in E-Prime at all (from looking at the documentation it appears not to be!) then it would certainly be “non-trivial”.

Lab-based studies
------------------

Both PsychoPy and E-Prime were designed for in-lab studies and can interact with a range of hardware including EEG, fMRI and eye tracking devices although, for E-Prime, most of these devices require a plugin and incur an additional $1,995.00 charge for each.

Note also that E-Prime only runs on Windows, whereas PsychoPy runs on Windows, Mac and Linux (or any device with a browser, if you use the JavaScript/Pavlovia output option).

Web-based studies
------------------

PsychoPy experiments can output either Python (for local studies) or JavaScript scripts (for web-based studies). These can run in any device with a modern browser, including Windows, Mac, Linux, iOS, Android, and ChromeOS. When PsychoPy studies run on the web, using Pavlovia.org, you send participants a link to the study, they open it in their browser and the data files are automatically sent back to your Pavlovia account. These web-based studies can also connect seamlessly to Pavlovia Surveys, for Qualtrics-style surveys and questionnaires.

E-Prime is Windows-only and doesn't have a JavaScript output option, so it can't be used for browser-based studies. During the pandemic of 2020, PSTNet did introduce E-Prime Go, which allows E-Prime experiments to be compiled into self-contained apps that can be sent to participants to run on their own machines. Again, the participant must be running Windows and when the study is completed the must follow whatever instructions you give them to send the data back to you. This is a much more cumbersome process than the automatic data collection that Pavlovia provides. 

Timing
------

Both E-Prime and PsychoPy have excellent timing, as can be seen in the `Timing megastudy (Bridges et al, 2020)`_.
PsychoPy is also unique in providing `Timing Validator`_ components to allow easy checking of stimulus timing during experiment execution, on relatively cheap hardware such as the Cedrus Riponda button box. This means that, even if your operating system or monitor causes timing issues that the software cannot know about, these can be automatically detected by the PsychoPy using the validator hardware.

.. _Timing Megastudy (Bridges et al, 2020): https://peerj.com/articles/9414/
.. _Timing Validator: https://psychopy.org/builder/components/VisualValidatorRoutine.html#visualvalidatorroutine

Surveys
-------

E-Prime isn't really suited to creating surveys. Although one could manually create each question on its own page, this wouldn't be as powerful as dedicated tools, such as Qualtrics.

PsychoPy's Python library also has somewhat limited built-in support for survey-style studies but, when used in web-based studies, PsychoPy has the added benefit of being able to connect with Pavlovia surveys which are purpose built for this and do have roughly feature parity with Qualtrics. You can create a survey using Pavlovia Survey creator in the browser and even import a Qualtrics .qsf file.

Updates
-------

New versions of PsychoPy are released frequently, with major versions twice per year and bug-fix updates frequently in between. E-Prime, by comparison, has major releases very rarely indeed and its `last bug-fix release was in 2024 <https://support.pstnet.com/hc/en-us/articles/360009483234-RELEASE-INFO-E-Prime-3-0-Change-History-27275>`__ although there is a `list of known issues <https://support.pstnet.com/hc/en-us/articles/360009608053-RELEASE-INFO-Known-Issues-in-E-Prime-3-0-27789>`__.

Pricing and vendor lock-in
--------------------------

E-Prime costs roughly $995 per concurrent license, and adds a further $1,995.00 if you want to use a plug-in for EEG or eye-tracking extensions (for each extension). Its experiment file formats are proprietary and its programming language (Visual Basic) is no longer widely used in any other context.

PsychoPy is free and open-source software. Running studies online using Pavlovia does incur a small charge but even that is small compared to standard lab use of E-Prime (|price.university.credit| per respondent or |price.university.licenceonly| for an unlimited institutional licence). PsychoPy also offers paid consultancy and training options. PsychoPy uses the Python language which is widely used in many other contexts, and its experiment file formats are open and human-readable (XML-based and with a public format description). 

Community
---------

E-Prime is historically the more widely-used option, having been very much the dominant package in the early 2000s, when PsychoPy was just being conceived.

While it isn't clear how many users E-Prime still has now, `PsychoPy has over 50,000 monthly active users <https://usage.psychopy.org>`_ and a very active `users forum <https://discourse.psychopy.org/>`_ with over 15,000 members.