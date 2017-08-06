# three-asciiffect
A fork of the ascii effect for npm package

ThreeJS AsciiEffect as an npm module. 

```js

var AsciiEffect = require('three-asciieffect')

function start(gl, width, height) {
    renderer = new THREE.WebGLRenderer({
        canvas: gl.canvas
    })
    renderer.setClearColor(0x000000, 1.0)

    scene = new THREE.Scene()
    camera = new THREE.PerspectiveCamera(50, width/height, 1, 1000)
    camera.position.set(0, 1, -3)
    camera.lookAt(new THREE.Vector3())

    asciiEffect = new AsciiEffect(renderer);

    var geo = new THREE.BoxGeometry(1,1,1)
    var mat = new THREE.MeshBasicMaterial({ wireframe: true, color: 0xffffff })
    var box = new THREE.Mesh(geo, mat)
    scene.add(box)
}

function render(gl, width, height) {
    asciiEffect.render(scene, camera);
}
```


#### `AsciiEffect = require('three-asciieffect')`

This module exports a function which returns an AsciiEffect class. This allows you to use the module with CommonJS, globals, etc.


The returned function has the following constructor pattern:

```js
asciiEffect = new AsciiEffect(renderer, charSet, options)
```
