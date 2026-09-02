.. include:: /price_defs.rst

.. _psychopyVersusJsPsych:

Comparing PsychoPy with jsPsych
=====================================

jsPsych is a JavaScript-based library for creating web-based experiments. PsychoPy is designed to run studies either in web-based environments (using JavaScript) or in the lab (using Python), where you benefit from millisecond timing and hardware connections (e.g. for neuroimaging, or eyetracking studies) that jsPsych can't provide.

Unlike PsychoPy, jsPsych doesn't have a graphic user interface, so you do need to be comfortable with coding in JavaScript. PsychoPy allows you to choose to hand-write your scripts, to use the Builder graphical interface , or to combine snippets of code with Builder which is what most people do to maximise ease and flexibility.

Flexible, dynamic parameters
----------------------------

jsPsych offers a range of “plugins” that allow you to create your study at the level of, essentially, a trial. For instance, if you want to collect the response of a participant to an image using the keyboard you would insert the `image-button-response` plugin and set the 14 or so settings for that plugin, such as stimulus size and position. What if you want two stimuli presented one after the other? Then you would use the `same-different-image`. What if you wanted to present a fixation point before, or in between, the two images… ah. Now you need to write your own code. What if you want to parametrically vary the orientation of the stimulus? Unfortunately, orientation isn't a setting, so you'll need to write your own.

In PsychoPy the researcher gets to manipulate a more granular level, with settings for every stimulus and every response object. There are no "types" of trials (although there are some handy built-in templates) because the researcher is in control of what each routine is doing. PsychoPy stimuli support a very rich set of parameters (contrast, opacity, dimensions, orientation), all of which can be controlled independently. So, if you want multiple stimuli in your trial, just add them, as many as you like, and you can choose whether they come one after the other or one next to the other on screen. Not only that, nearly all PsychoPy parameters can also be updated not only on every trial but on every screen refresh! That means stimuli can be made to move, resize, bounce, or alter their transparency constantly, making for more dynamic interactive experiments. Unlike jsPsych, the stimuli being rendered by PsychoPy are also rendered in high-performance hardware-accelerated graphics (WebGL), which is why everything can be updated constantly, between screen refreshes.

In short, in jsPsych you largely have to write the code to your own stimuli and you are probably limited in what can be achieved. In PsychoPy, even advanced experiments can be created with very little (if any) code, and these are more easy to share and re-use because other researchers (and "future you") can see exactly what was done in the Builder interface, rather than having to read and understand a long script.

Lab-based studies
------------------

PsychoPy is a Python-based desktop app so, for local lab-based experiments, you can connect with external devices such as EEG, eye trackers, fMRI and photometers relatively easily (anything possible with python code can be done in PsychoPy). 
jsPsych is a browser based tool so it typically cannot directly communicate with external device ports like serial ports without an additional bridge software to connect the browser and the hardware. 
Timing is also less good in browser-based studies, because JavaScript has poorer knowledge of when the screen has refreshed, as detailed in the `Timing Megastudy (Bridges et al, 2020)`_.

.. _Timing Megastudy (Bridges et al, 2020): https://peerj.com/articles/9414/

Surveys
--------

Both PsychoPy and jsPsych have options for presenting surveys and questionnaires and both are based on the survey.js library. That means that the range of question types available in both platforms are very similar. Pavlovia.org provides an in-browser user interface to create and deploy surveys and questionnaires without the need for direct coding (although direct editing of the .json file is possible) whereas survey implementation with jsPsych would typically be code-based and require a hosting method (see pricing section). 

Pricing
--------

Both PsychoPy and jsPsych are free and open-source, meaning you can run in-lab studies for free with both platforms. For online studies requiring a server, you can host studies made on either platform on Pavlovia.org. Pavlovia is a paid for service, but with minimal costs (|price.university.credits| per participant or |price.university.licenceonly| for a whole institute unlimited use). 

With jsPsych, there is an option for free with Jatos and MindProbe (although this comes with no security certifications, whereas Pavlovia is ISO 27001 certified for institutions that need secure data collection). jsPsych studies can also run on cognition.run where unlimited task uploads costs $2990/per year. Or you can self-host a Jatos server, but then the staff time required might be more expensive and, again, the security would likely be less strong if you aren't very highly trained in server security maintenance (independent penetration testing, for instance, costs thousands of pounds).

Both PsychoPy and jsPsych have free community support forums and benefit from an enthusiastic community of open-source supporters, and there are also options with both platforms to pay for professional support if desired. For PsychoPy and Pavlovia we charge |price.university.support| an hour or support can be added onto your Pavlovia institute licence, and for jsPsych you can contact the creators directly for a quote or you can purchase organisation level support with Mindprobe for 5000 Euros per year.
