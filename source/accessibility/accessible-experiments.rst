**How to create accessible experiments?**
-------------------------------
If you are working with a specific population or clinical group, you might want to adapt your experiment in various ways to make it easy for your sample to interact with. 

**Resources:**

﻿`W3C Accessibility Principles <https://www.w3.org/WAI/fundamentals/accessibility-principles/>`__ 

﻿`W3C How to meet WCAG (Quickref) <https://www.w3.org/WAI/WCAG22/quickref/>`__

﻿`Europa POUR-CAF principles: Accessible colour palettes <https://data.europa.eu/apps/data-visualisation-guide/accessible-colour-palettes﻿>`__

`Section 508: Fonts and typography <https://www.section508.gov/develop/fonts-typography/>`__


Add text-to-speech and read aloud features
===============================
*Tags: Accessibility for those with sight or reading difficulties*

Text-to-speech applications (e.g. `NVDA <https://www.nvaccess.org/>`__) are not compatible with running |PsychoPy| experiments (or PsychoJS experiments running in browser). However, you can easily add sound components to your routine that caption any text, narrate instructions, or describe non-text content (e.g. images, graphs, or videos). A demo experiment in which text is read aloud upon clicking on it can be found `here <http://pavlovia.org/Consultancy/text_speech>`__.


Add volume adjustments
===============================
*Tags: Hearing accessibility*

Allow the participant to select the volume at which the sound is presented, to ensure it is at an appropriate level. You can start your experiment by presenting a sample sound in a loop and ask the participant to adjust their device volume to a comfortable level (and press a key or click an onscreen button to confirm the volume is at a comfortable level). Alternatively, you can ask your participant to use the keyboard or on-screen buttons to adjust the PsychoPy volume of sound components directly and then use this volume in all sound components throughout the task. A demo in which the participant can adapt the volume of a white noise recording with an on-screen slider can be found `here <https://pavlovia.org/InesJP/volume_master>`__.


 
Use appropriate colour palettes 
===============================
*Tags: Accessibility for those with sight difficulties*

Use colourblind-friendly palettes and high contrast in your experiments' visual components. This includes stimuli components (e.g. text, polygons, images, videos…) but also responses (e.g. mouse, slider, textbox…). You can get more information about accessible colour palettes `here <https://data.europa.eu/apps/data-visualisation-guide/accessible-colour-palettes>`__. 
General recommendations include using blues with reds or oranges, as they are the most colourblind-friendly combination.
You could also allow your participant to choose a bespoke colour palette for your experiment; a demo in which the participant can modify the text and background colours can be found `here <https://pavlovia.org/Consultancy/text_contrast>`__.


Allow participants to adjust font or stimulus size
===============================
*Tags: Accessibility for those with sight difficulties*

Ensure that the height unit you are using is appropriate to be read or seen on multiple screen sizes. For text, you can modify letter height in the Formatting tab within the component. For images, you can modify the size of stimuli in the Layout tab. You could also allow participants to choose the side of the text (demo `here <https://pavlovia.org/Consultancy/text_size>`__) or images (demo `here <https://pavlovia.org/Consultancy/cursor_size>`__). 

Accessible font choices
===============================
*Tags: Accessibility for those with sight difficulties*

Use a Sans Serif font (i.e., without decorative strokes) to facilitate readability (you can find some guidance on font recommendations `here <https://www.section508.gov/develop/fonts-typography/>`__). Sans Serif fonts include Arial, the default font of PsychoPy text. They also include Calibri, Open Sans, or Verdana. You can modify the font by typing its name in the formatting setting window of the text component. If you do not have a specific font installed, PsychoPy will ask you to download it.
 
Add sign language videos or text transcriptions for audio content
===============================
*Tags: Accessibility for those with listening difficulties*

You can add a video component to your routine that translates your audio content to sign language, or include a text component of sufficient contrast and size (demo `here <https://pavlovia.org/Consultancy/text_contrast>`__) that displays the dictation of the audio (demo `here <http://pavlovia.org/Consultancy/text_speech>`__).
When possible, pair audio cues with visual ones.

Operable user interface
===============================
*Tags: Accessibility for those with sight or mobility difficulties*

Avoid using high-dexterity inputs, such as touch screen or mouse clicks, to advance the experiment or record your responses. Instead, use lower-dexterity interfaces such as large buttons, a keyboard, or sound sensors.

If you need a mouse click, make sure the cursor is a high-contrast colour (recommendations `here <https://data.europa.eu/apps/data-visualisation-guide/accessible-colour-palettes>`__) and large enough to be visible to everyone. You can add a cursor image and set its position to `mouse.getPos()` every frame, and adapt its size and colour as needed. You can also allow the participant to adapt the mouse image size (demo `here <https://pavlovia.org/Consultancy/cursor_size>`__).
 
Time experiments appropriately 
===============================
*Tags: Accessibility for those with focus or learning difficulties*

Allow users to decide when to move to the next routine. To avoid the routine finishing by itself, leave the duration setting of your routine empty. To allow the routine to finish when pressing a keyboard key, create a keyboard response with no duration, “Force end of routine” ticked, “Register keypress on…” press, and select whichever allowed keys you specify to the user (e.g. ‘space’).

Allow users to repeat the instructions (either text and/or sound). A demo experiment in which the audio is repeated whenever ‘r’ is pressed can be found `here <https://pavlovia.org/InesJP/text_speech_loop>`__.

You can also allow participants to move forwards and backwards through instruction slides. You can find a tutorial on this `here <https://www.youtube.com/watch?v=CvjvqLZHXrs>`__. 
 
Avoid photosensitive content
===============================
*Tags: Accessibility to avoid seizures*

Avoid content that flashes. If flashing content is necessary, warn users before it appears and, if possible, let them skip that routine, e.g. by pressing a specific key. To do so, create a keyboard response with no duration, “Force end of routine” ticked, “Register keypress on…” pressed, and select whichever allowed keys you specify to the user (e.g. ‘space’).
 
Information must be easy to understand
===============================
*Tags: Accessibility for those with focus or learning difficulties*

Use clear, simple language.
Define complex concepts and unusual words.

