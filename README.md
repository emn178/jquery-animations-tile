# jQuery-animations-tile
A plugin of [jQuery-animations](http://emn178.github.io/jquery-animations/) that provides tile animations.

## Download
[Compress](https://raw.github.com/emn178/jquery-animations-tile/master/build/jquery.animations-tile.min.js)  
[Uncompress](https://raw.github.com/emn178/jquery-animations-tile/master/src/jquery.animations-tile.js)

## Demo 
[Tile](http://emn178.github.io/jquery-animations-tile/samples/tile/)  

## Browser Support
jQuery-animations currently supports IE10+, Chrome, Firefox, Safari and Opera.

## Options
###### *rows: `Number` (default: `1`)*
Sets rows of tiles.

###### *cols: `Number` (default: `1`)*
Sets columns of tiles.

###### *effect: `String` or `Array` or `Function` (default: `"flyOut"`)*
Sets animations to tiles, multiple for alternate. You can also use a function to calculate which effect to use. The function should be defined like this.
```
function func(options, row, col)
{
  return 'effect';
}
```

###### *sequent: `Boolean` (default: `true`)*
Sets the flag determining the animations of tiles run with different delays. It will be duration / tile count.

###### *sequence: `String` or `Array` (default: `"random"`)*
Sets the sequence method or custom orders to run the animations of tiles. Available methods:  

*random*: random tiles  
*randomCols*: random columns  
*randomRows*: random rows  
*lr*: left to right  
*rl*: right to left  
*tb*: top to bottom  
*bt*: bottom to top  
*lrtb*: left to right and top to bottom  
*rlbt*: right to left and bottom to top  
*rltb*: right to left and top to bottom  
*lrtb*: left to right and top to bottom  
*lrbt*: left to right and bottom to top  
*tblr*: top to bottom and left to right  
*btrl*: bottom to top and right to left  
*tblr*: top to bottom and left to right  
*tbrl*: top to bottom and right to left  
*btlr*: bottom to top and left to right  

###### *groups: `Number` (default: `1`)*
Sets groups to separate so that tiles of groups have the same delay time.

###### *adjustDuration: `Boolean` (default: `true`)*
Sets the flag determining the animations of tiles run with different duration. It will try to complete all animations of tiles in duration of entire animation.

## Example
Basic usage
```JavaScript
$('#want-to-animate').animate('tile', {
  rows: 2,
  cols: 2
});
```
Effects
```JavaScript
$('#want-to-animate').animate('tile', {
  rows: 2,
  cols: 2,
  effect: [
    'flyToUp', // for even tile
    'flyToDown fadeOut' // for odd tile
  ]
});
```
Effects by function
```JavaScript
$('#want-to-animate').animate('tile', {
  rows: 2,
  cols: 2,
  effect: function(options, row, col) {
    if(row == col)
      return 'flyToUp';
    else
      return 'flyToDown';
  }
});
```
Sequence
```JavaScript
$('#want-to-animate').animate('tile', {
  rows: 2,
  cols: 2,
  sequence: [
    [
      [0, 0]  // tile
    ], // group, all tiles have same animation in the same group
    [[1, 1]], 
    [[0, 1]], 
    [[1, 0]]
  ]
});
```

## License
The project is released under the [MIT license](http://www.opensource.org/licenses/MIT).

## Contact
The project's website is located at https://github.com/emn178/jquery-animations-tile  
Author: emn178@gmail.com
