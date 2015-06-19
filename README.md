# AudioFade
jQuery plugin for manipulating audio as you scroll

### Dependancies
jQuery 1.2.6 or later

### What can it do?
AudioFade is for playing different sounds and fading them in and out again as you scroll down the page. It can also play sounds immediately, without a fade needed.

### Setting it up
Just link to AudioFade after jQuery:

```
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
<script src="js/AudioFade.js"></script>
```

Then add your `<audio>` element to the HTML, including the `loop` attribute if you want the sound to keep looping:

```
<audio loop id="sound1" src="sound1.mp3"></audio>
<audio loop id="sound2" src="sound2.mp3"></audio>
<audio id="sound3" src="sound3.mp3"></audio>
```

Finally, just declare a new AudioFade object and initiate it:

```
var a = new AudioFade('#elementId', 300, 900, 200).init();
```

### Documentation
The syntax for the AudioFade object is pretty simple:

```
var someVariable = new AudioFade(elementId, fadeIn, fadeOut, fadeDuration).init();
```

The elementId value is a jQuery selector. The fadeIn, fadeOut, and fadeDuration values are in pixels. The fadeIn will tell AudioFade when to start playing the sound, and if it has a fade, when to start fading in.

The fadeOut value defines when the sound will start fading out. The fadeDuration defines how many pixels the fade will last. If you don't define it, it defaults to 500px.

If you want to just play one sound once, with no fade effect, then you would leave off the `loop` attribute from the audio element and define the object using a fadeIn value only. for example:

```
var a = new AudioFade('#sound1', 850).init();
```

Otherwise, if you want a consistant looping background track in one portion of the webpage, you could do this:

```
var b = new AudioFade('#song1', 500, 3000).init();
```

In the above example, the fades would last for 500 pixels as per the default.

### What's to come
* More intuitive duration definitions, ie "fast", "slow", etc.
* Control based on element position in the viewport and not the pixel position.
* ...
