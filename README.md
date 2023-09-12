# Tugas1Grafkom
Untuk 3 jenis lighting hampir memiliki contoh code yang sama, readme kali ini akan menjelaskan salah satu code dari jenis lighting yakni code directional lighting.

-- Directional Lighting

#index.html
<link rel="stylesheet" href="style.css">
//digunakan untuk menghubungkan ke file CSS eksternal yang disebut "style.css".

<canvas id="canvas"></canvas>
<div id="uiContainer">
  <div id="ui">
    <div id="fRotation"></div>
  </div>
</div>
<!-- vertex shader -->
<script  id="vertex-shader-3d" type="x-shader/x-vertex">
attribute vec4 a_position;
attribute vec3 a_normal;

uniform mat4 u_worldViewProjection;
uniform mat4 u_worldInverseTranspose;

varying vec3 v_normal;

void main() {
  // Multiply the position by the matrix.
  gl_Position = u_worldViewProjection * a_position;

  // orient the normals and pass to the fragment shader
  v_normal = mat3(u_worldInverseTranspose) * a_normal;
}
</script>
<!-- fragment shader -->
<script  id="fragment-shader-3d" type="x-shader/x-fragment">
precision mediump float;

// Passed in from the vertex shader.
varying vec3 v_normal;

uniform vec3 u_reverseLightDirection;
uniform vec4 u_color;

void main() {
  // because v_normal is a varying it's interpolated
  // so it will not be a unit vector. Normalizing it
  // will make it a unit vector again
  vec3 normal = normalize(v_normal);

  float light = dot(normal, u_reverseLightDirection);

  gl_FragColor = u_color;

  // Lets multiply just the color portion (not the alpha)
  // by the light
  gl_FragColor.rgb *= light;
}
</script><!--
for most samples webgl-utils only provides shader compiling/linking and
canvas resizing because why clutter the examples with code that's the same in every sample.
See https://webglfundamentals.org/webgl/lessons/webgl-boilerplate.html
and https://webglfundamentals.org/webgl/lessons/webgl-resizing-the-canvas.html
for webgl-utils, m3, m4, and webgl-lessons-ui.
-->
<script src="https://webglfundamentals.org/webgl/resources/webgl-utils.js"></script>
<script src="https://webglfundamentals.org/webgl/resources/webgl-lessons-ui.js"></script>
<script src="https://webglfundamentals.org/webgl/resources/m4.js"></script>

<script src="script.js"></script>
