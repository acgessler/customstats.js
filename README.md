customstats.js
==============

JavaScript Stats Overlay for displaying custom measurements, strongly based on mrdoob's [stats.js](github.com/mrdoob/stats.js) but without any timing or measurement code. 

![Example](http://s17.postimg.org/yq41y3t4b/statsshot.png)

This is an example of three `CustomStatDisplay` stacked on top of each other displaying triangle count, batch count and fps rate of a WebGl application.

How to use
----------

After including `customstats.js` into your page, create as many instances of `CustomStatsDisplay` as you like. The display overlay automatically inserts itself into the DOM using absolute placement (i.e. relative to the upper-left corner of the screen). 

    // All configuration options have default values.
    var stats = new CustomStatsDisplay({
				  caption 	: 'fps'  
				, width		: 140
				, left 		: 0
				, top 		: 0
				, style     : 0
				
				, range : [0, 100] // (initial) range of the display
				, autorange	: 50 // automatically adjust display range every 50 updates
	  });
	  
`range` and `autorange` are also available as member functions on the stats object and can thus be changed at any time.
	  
To feed new values into the display, call `stats.update(sample)` regularly. Each update becomes a bar in the display. Note that updating the display involves DOM changes, so to avoid excessive CPU use it is recommended to throttle updating to about 10 updates/second.

If `autorange` is set to a non-zero value, the range displayed by the display is automatically adjusted to fit the actual range of values every `n` updates. Otherwise, the range must be set using the `range` configuration option.

Measured values are always coerced to integers.

Contributing
----------

This is by no means finished, it is more a rough draft to serve my current needs. Any contributions are welcome!
