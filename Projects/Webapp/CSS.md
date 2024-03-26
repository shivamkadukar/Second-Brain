
__Flexbox__
![[Pasted image 20240110213020.png]]

__Alignment Properties__
- justify-content. For item alignment on main axis.
- align-items. For item alignment on cross axis.
- align-self. For unique flex items on cross axis.
- align-content. Used for packing flex lines and control over space.

### CSS Units of measurements
__Absolute Values__
They are not so suitable when it comes to the wide variety of devices in use today that have different viewport sizes. Because of this, absolute units are used when the size of the web page is known and will remain constant.

|**Unit**|**Name**|**Comparison**|
|---|---|---|
|Q|Quarter-millimeters|1Q = 1/40th of 1cm|
|mm|Millimeters|1mm = 1/10th of 1cm|
|cm|Centimeters|1cm = 37.8px = 25.2/64in|
|in|Inches|1in = 2.54cm = 96px|
|pc|Picas|1pc = 1/6th of 1in|
|pt|Points|1pt = 1/72nd of 1in|
|px|Pixels|1px = 1/96th of 1in|
of these, the pixels and cm are most frequently used for defining

__Relative Values__

|**Unit**|**Description and relativity**|
|---|---|
|em|Font size of the parent where present.|
|ex|x-co-ordinate or height of the font element.|
|ch|Width of the font character.|
|rem|Font size of the root element.|
|lh|Value computed for line height of parent element.|
|rlh|Value computed for line height of root element which is <html>.|
|vw|1% of the viewport width.|
|vh|1% of the viewport height.|
|vmin|1% of the smaller dimension of viewport.|
|vmax|1% of the larger dimension of viewport.|
|%|Denotes a percentage value in relation to its parent element.|