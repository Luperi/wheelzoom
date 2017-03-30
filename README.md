# Wheelzoom #

Based on [this script](http://www.jacklmoore.com/wheelzoom/), which is no longer manteined.

This is a pure Javascript library for zooming IMG elements with the mousewheel/trackpad. Wheelzoom works by replacing the img element's src with a transparent image, then using the original src as a background image, which can be sized and positioned. Wheelzoom doesn't add any extra elements to the DOM, or change the positioning of the IMG element.

## DEMO ##
[Here](https://luperi.github.io/wheelzoomdemo/) you can find a full usage example, enjoy :)

## Usage ##
### Supported Browsers ###
Chrome, Safari, Opera, FireFox 17+, IE9+.

### Instantiate wheelzoom ###

    wheelzoom(document.querySelectorAll('img'));
    
    // set zoom percent
    wheelzoom(document.querySelectorAll('img'), {zoom:0.05});
    
    // set max-zoom scale
    var images = wheelzoom([
        document.getElementById('img-1'),
        document.getElementById('img-2'),
    ], {zoom:0.05, maxZoom:20});

### Subscribe for events ###

    images[0].addEventListener('wheelzoom.reset', function(e) {
    	console.log('wheelzoom.reset fired');
    });

### Fire events ###

    triggerEvent(images[0], 'wheelzoom.destroy');

### Events available ###

|Event name            | Description                                                                            |
|:------------------   |:---------------------------------------------------------------------------------------|
|`wheelzoom.reset`     | Fired when image zoom level return to zero.                                            |
|`wheelzoom.destroy`   | Firing this event is possible to reset wheelzoom behaviour (see above example).        |
|`wheelzoom.in`        | Fired when image is zoomed in (see full demo example).                                 |  
|`wheelzoom.out`       | Fired when image is zoomed out (see full demo example).                                |
|`wheelzoom.dragstart` | Fired when start dragging on the image (see full demo example).                        |
|`wheelzoom.drag`      | Fired when image is dragged (see full demo example).                                   |
|`wheelzoom.dragend`   | Fired when end dragging on the image (see full demo example).                          |

## License ##
[MIT License](http://opensource.org/licenses/MIT)
