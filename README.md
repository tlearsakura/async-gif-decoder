# Async GIF decoder [![Build Status](https://travis-ci.org/honzabrecka/async-gif-decoder.svg?branch=master)](https://travis-ci.org/honzabrecka/async-gif-decoder)

An asynchronous GIF decoder written in ActionScript 3, which lets you play animated GIFs in flash without freezing the UI.

> Inspired by Lee Burrows' [Async-Image-Encoders](https://github.com/LeeBurrows/Async-Image-Encoders), based on Thibault Imbert's [as3gif](https://code.google.com/p/as3gif/).

```as3
var gif:GIF = new GIF();
    gif.addEventListener(Event.COMPLETE, function(event:Event):void
    {
        trace("done", gif.totalFrames);
        gif.play();
    });
    gif.addEventListener(IOErrorEvent.IO_ERROR, function(event:Event):void
    {
	    trace(event);
    });
    gif.load(new URLRequest("smile.gif"));

addChild(gif);
```