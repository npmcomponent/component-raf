*This repository is a mirror of the [component](http://component.io) module [component/raf](http://github.com/component/raf). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/component-raf`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*

# raf

  request animation frame

## Installation

    $ component install component/raf

## Example

  Request the animation frame with `raf(fn)`, cancel with `raf.cancel(id)`.

```js
var x = 0;
var y = 50;
var canvas = document.querySelector('canvas');
var ctx = canvas.getContext('2d');
var raf = require('raf');

function animate() {
  raf(animate);
  draw();
}

var prev = Date.now();
function draw() {
  var curr = Date.now();
  var diff = curr - prev;
  var p = diff / 16;
  ctx.clearRect(0, 0, 900, 300);
  ctx.beginPath();
  ctx.globalAlpha = .5;
  ctx.arc(x, y, 10, 0, Math.PI * 2, false);
  ctx.fill();
  x += 2;
  y += Math.sin(x/20) * 5;
  prev = curr;
}

animate();
```

## License

  MIT
