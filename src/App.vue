<template>
  <div id="app">
    <h1>SVG Line Drawing Animation</h1>
    <h2>A Javascript-free way of animating SVG's</h2>
    <svg v-if='imageLoaded["image-1"]' id="image-1" :data-run="imageRunner['image-1']" class="draw animation" viewBox="0 0 105.8 105.8">
      <g fill="none" stroke-width="1.3">
        <path pathLength="3000" stroke="#faa" d="M52.7 77c.9-.7 2-1 3-1 3 0 5.4 2.4 5.4 5.4M46.6 55c2 .8 3 2.7 3.3 5 0 2-1.3 3.8-3.3 5l6 12c-1.4 1-2 2.5-2.3 4.4a5.4 5.4 0 0 0 10.8 0l19-.4c0-3 2.5-5.4 5.5-5.4M80.2 81a5.4 5.4 0 1 0 5.4-5.4L83 50.3a5.4 5.4 0 1 1 0-10.8 5.4 5.4 0 0 1 0 10.8M40.7 63.8a5.4 5.4 0 0 1 0-7.7M21.9 84.8a5.4 5.4 0 0 1-3.8 9.2 5.4 5.4 0 1 1 3.8-9.2l18.8-21a5.4 5.4 0 0 0 5.9 1.1m10-32.3c-1.9-.8-3.2-3-3.2-5a5.4 5.4 0 1 1 3.3 5L46.6 55a5.4 5.4 0 0 0-6 1.1l-8.8-14a5.4 5.4 0 0 1-9.2-3.7 5.4 5.4 0 1 1 9.2 3.8"/>
        <path pathLength="3000" stroke="#000" d="M55.3 73.5a5.4 5.4 0 0 1 8.4 4.5M49.2 51.6c2 .8 3.1 2.7 3.3 5 0 2-1.2 3.8-3.3 5l6.1 12C54 74.5 53.2 76 53 78a5.4 5.4 0 0 0 10.8 0l19.1-.4c0-3 2.4-5.4 5.4-5.4m-5.4 5.4a5.4 5.4 0 1 0 5.4-5.4L85.8 47a5.4 5.4 0 1 1 0-10.8 5.4 5.4 0 0 1 0 10.8M43.3 60.4a5.4 5.4 0 0 1 0-7.7M24.6 81.4a5.4 5.4 0 0 1-3.8 9.2 5.4 5.4 0 1 1 3.8-9.2l18.7-21a5.4 5.4 0 0 0 6 1.1m10-32.3c-2-.8-3.2-3-3.3-5a5.4 5.4 0 1 1 3.3 5l-10 22.4a5.4 5.4 0 0 0-6 1.1l-8.8-14a5.4 5.4 0 0 1-9.2-3.7 5.4 5.4 0 1 1 9.2 3.8"/>
      </g>
    </svg>
    <svg v-else id="image-1" >Loading</svg>
    <button @click="runAgain('image-1')">Run Again</button>
    <p>All the animations on this page can be created with just CSS and inline SVG</p>
    <p>What is needed is an SVG with a 'path' element. Simply add the property 'pathlength' to eath 'path' element and set it to a value - say 1000. Then the following CSS making sure the 'stroke' numbers are significantly greater than the path lengh:</p>
    <pre><code>.my-svg{
  stroke-dasharray: 2000;
  stroke-dashoffset: 2000;
  animation: draw 5s linear forwards;
}
@keyframes draw {
  to {
    stroke-dashoffset: 0;
  }
}</code></pre>
    
    <svg v-if='imageLoaded["image-2"]' id="image-2" :data-run="imageRunner['image-2']" class="un-draw animation" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 105.8 105.8">
      <path pathLength="1000" fill="none" stroke="gray" stroke-linejoin="round" stroke-width=".7" d="M65.9 65.9c-84.7 84.7 105.9-28.3-12.4-9.6-118.3 18.7 97.9 67.3-8.9 13-106.7-54.5 59.7 92 5.3-14.8C-4.5-52.3 16.1 168.4 35 50c18.7-118.3-69 85.1 15.6.4 84.7-84.7-118.7 3.1-.4-15.6C168.4 16-52.3-4.5 54.5 49.9c106.7 54.4-39.6-112 14.7-5.3 54.4 106.8 5.8-109.5-12.9 8.9-18.7 118.3 94.3-72.3 9.6 12.4z"/>
    </svg>
    <svg v-else id="image-2">Loading</svg>
    <button @click="runAgain('image-2')">Run Again</button>
    <p>The SVG animation can even be played backwards (un-drwaing) with the following css.</p>
    <pre><code>my-svg{
  stroke-dasharray: 2000;
  stroke-dashoffset: 0;
  animation: un-draw 5s linear forwards;
}
@keyframes un-draw {
  to {
    stroke-dashoffset: -2000;
  }
}</code></pre>
    <svg v-if='imageLoaded["image-3"]' id="image-3" :data-run="imageRunner['image-3']" class="draw animation" viewBox="0 0 106.658 106.658" xmlns="http://www.w3.org/2000/svg">
      <g class="show-after" :data-run="imageRunner['image-3']">
        <path fill="navy" d="M46.26 64.94c-11.04.43-21.13 5.72-30.68 10.83-2.39 1.53-5.25 2.58-7.16 4.73-.48 2.05 1.82 3.5 2.75 5.1 8.94 11.7 22.92 19.5 37.61 20.66 8.45.38 17.12-.35 24.9-3.92 2.32-1.17 5.04-1.88 6.97-3.66.87-2-1.77-2.28-2.97-2.83-3.79-2.76-5.57-7.27-7.98-11.14-3.91-7.12-8.26-14.93-15.98-18.47-2.35-1-4.92-1.35-7.46-1.3z"/>
        <path fill="navy" d="M68.5 2.66c-1.95.11-5.16-.43-3.69.16C70.32 7 77.91 16.41 78.86 23.27c.4 4.64.26 9.45-1.8 13.81-2.9 7.23-9.5 12.73-16.98 14.88-3.62 1.06-7.5.49-11.18.49-11.12-1.84-20.34-11.69-21.25-22.97-.5-1.7.6-4.83-1.78-5.36-2.34.46-3.33 3.16-4.62 4.9a97.8 97.8 0 0 0-9.78 25.44c-.47 3.61-1 7.5.25 11 .54 1.6 2.38 2.17 3.66 1.01 7.98-4.56 16.58-8.44 25.74-9.78 5.58-.63 11.52-.3 16.49 2.72 9.53 5.51 15.18 15.32 21.9 23.65 1.18 1.62 3.07 0 3.22-1.52.78-2.93 2.94-6.52 6.5-5.94 3.44.38 5.83 3.14 8.6 4.88 2.1.1 2.4-2.63 3.29-4.03 3.36-7.12 5.46-14.92 5.11-22.85a45 45 0 0 0-2.9-18.1C97.88 20.1 84.98 7.34 69.24 2.71a3.06 3.06 0 0 0-.73-.06z"/>
        <path fill="orange" d="M51.72.3C33 .62 14.99 11.8 6.42 28.45a53.33 53.33 0 0 0-3.16 42.6C4.5 74.38 5.7 77.93 8 80.63c1.93.52 3.48-1.7 5.23-2.43 8.74-4.97 17.88-9.8 27.79-11.71 5.55-1.2 11.91-.74 16.48 3.05C65.26 76 68.48 86.15 74.45 94.12c1.83 2.68 5.51 4.23 8.51 2.51 4.81-2.25 8.11-6.71 11.38-10.74 1.28-1.92 3-3.75 3.54-6.01-2.17-2.8-5.63-4.93-9.23-5.25-3.66-.27-5.78 3.27-6.7 6.31-.34.55-.42 1.98-1.04 2.04-4.37-4.47-7.44-10.06-11.65-14.7-5.18-6.23-12-11.95-20.38-12.73-9.73-.91-19.26 2.64-27.87 6.84-2.48 1.16-4.84 2.58-7.23 3.93-2.53-2.09-1.94-5.86-1.75-8.79 1.35-9.26 4.8-17.97 9.06-26.25 1.32-2.21 2.55-4.76 4.68-6.26 1.08.16.53 1.96.71 2.69.34 9.65 6.16 18.98 14.89 23.24.96.53 2.36 1.4 3.25.32 1.69 2.86 5.57 2 8.35 2.29 5.1.43 10.16-1.12 14.46-3.84 10.65-6.34 15.63-20.63 10.97-32.16C74.55 7.23 63.9-.17 52.82.28l-1.1.01zm7.8 31.7c3.19.07 5.2 3.55 4.1 6.42-1.02 3.68-6.95 4.27-8.55.68-1.8-2.77.13-6.9 3.5-7.08.32-.04.64-.05.96-.03z"/>
      </g>
      <g fill="none" stroke="#000" stroke-width="1.323">
        <path pathLength="1000" d="M53.329.661c29.087 0 52.668 23.58 52.668 52.668s-23.58 52.668-52.668 52.668C24.242 105.997.661 82.417.661 53.33.661 24.242 24.241.661 53.329.661"/>
        <path pathLength="1000" d="M53.329.661c14.544 0 26.334 11.79 26.334 26.334S67.873 53.33 53.329 53.33 26.995 41.54 26.995 26.995 3.773 61.866 13.773 66.945c0 0 23.243-15.4 39.906-9.904C70.342 62.538 80.424 88.93 81.898 82.71c3.69-15.57 15.769-2.672 15.769-2.672S86.309 99.58 78.156 96.607c-7.807-2.847-11.95-27.635-27.504-30.866C35.098 62.51 8.131 80.839 8.131 80.839"/>
        <path pathLength="1000" d="M64.526 36.739a5.345 5.345 0 0 1-5.345 5.345 5.345 5.345 0 0 1-5.346-5.345 5.345 5.345 0 0 1 5.346-5.345 5.345 5.345 0 0 1 5.345 5.345z"/>
        <path pathLength="1000" d="M45.282 51.706c-2.54-4.944-5.011-11.359-2.572-19.745 2.438-8.386-3.575-11.526-3.575-11.526"/>
      </g>
    </svg>
    <svg v-else id="image-3" >Loading</svg>
    <button @click="runAgain('image-3')">Run Again</button>
    <p>Other animations can also be used in conjunction with this to animate other parts of the svg - much like other HTML elements</p>
    <pre><code>other-svg-element{
  animation: fade-in 5s linear forwards;
}
@keyframes fade-in {
    0% { opacity: 0; }
    50% { opacity: 0; }
    60%   { opacity: 1; }
}</code></pre>
    <svg v-if='imageLoaded["image-4"]' id="image-4" :data-run="imageRunner['image-4']" class="draw animation" viewBox="0 0 105.83 105.83">
      <g fill="none" stroke="#000" stroke-linejoin="round" stroke-width="1.32">
        <path pathLength="800" d="M53.1 19.09H66.5v52.17h17.64L68.62 83.1 53.09 94.96 37.56 83.1 22.04 71.26h17.63V19.09H53.1"/>
        <path pathLength="1500" d="M24.27 10.85h5.07v19.69h6.65L30.13 35l-5.86 4.47-5.86-4.47-5.86-4.47h6.66V10.85h5.06"/>
        <path pathLength="1800" d="M81.91 28.7h5.07v19.69h6.65l-5.86 4.47-5.86 4.47-5.86-4.47-5.86-4.47h6.66V28.7h5.06"/>
      </g>
    </svg>
    <svg v-else id="image-4" >Loading</svg>
    <button @click="runAgain('image-4')">Run Again</button>
    <p>The following is a complete example using differing path lengths for different timings for the arrows.</p>
    <pre><code>    &lt;svg class=&quot;my-svg&quot; viewBox=&quot;0 0 105.83 105.83&quot;&gt;
      &lt;g fill=&quot;none&quot; stroke=&quot;#000&quot; stroke-linejoin=&quot;round&quot; stroke-width=&quot;1.32&quot;&gt;
        &lt;path pathLength=&quot;800&quot; 
          d=&quot;M53.1 19.09H66.5v52.17h17.64L68.62 83.1 53.09 94.96 37.56 83.1
          22.04 71.26h17.63V19.09H53.1&quot;/&gt;
        &lt;path pathLength=&quot;1500&quot;
          d=&quot;M24.27 10.85h5.07v19.69h6.65L30.13 35l-5.86
           4.47-5.86-4.47-5.86-4.47h6.66V10.85h5.06&quot;/&gt;
        &lt;path pathLength=&quot;1800&quot;
          d=&quot;M81.91 28.7h5.07v19.69h6.65l-5.86 4.47-5.86
           4.47-5.86-4.47-5.86-4.47h6.66V28.7h5.06&quot;/&gt;
      &lt;/g&gt;
    &lt;/svg&gt;</code></pre>
    <p>And the CSS:</p>
    <pre><code>.my-svg{
  stroke-dasharray: 2000;
  stroke-dashoffset: 2000;
  animation: draw 5s linear forwards;
}
@keyframes draw {
  to {
    stroke-dashoffset: 0;
  }
}</code></pre>
    <svg v-if='imageLoaded["image-5"]' id="image-5" :data-run="imageRunner['image-5']" class="draw animation" viewBox="0 0 210 210">
      <g fill="none" stroke-linejoin="round" stroke-width="2">
        <path pathLength="1000" stroke="#999" d="M57.292 69.59H30.031L16.4 45.981l13.631-23.609h27.261l13.631 23.609z"/>
        <path pathLength="1000" stroke="#999" d="M98.185 93.2H70.924L57.293 69.591l13.631-23.609h27.261l13.631 23.609z"/>
        <path pathLength="1000" stroke="#999" d="M57.292 116.8H30.031L16.4 93.191l13.631-23.609h27.261l13.631 23.609z"/>
        <path pathLength="1000" stroke="#999" d="M139.08 69.59h-27.262L98.187 45.981l13.631-23.609h27.261l13.631 23.609z"/>
        <path pathLength="1000" stroke="#999" d="M179.97 93.2h-27.261l-13.631-23.609 13.631-23.609h27.261l13.631 23.609z"/>
        <path pathLength="1000" stroke="#999" d="M179.97 140.41l-27.261-.00001-13.631-23.609 13.631-23.609h27.261l13.631 23.609z"/>
        <path pathLength="1000" stroke="#000" d="M125.45 187.63l-54.523-.00001-27.262-47.218 27.262-47.218h54.523l27.262 47.218z"/>
      </g>
    </svg>
    <svg v-else id="image-5" >Loading</svg>
    <button @click="runAgain('image-5')">Run Again</button>
    <p>Note, re-running animations, and timing the animations to trigger when visible does require javascript'.</p>
    <p>This page was created using Vue.js</p>

  </div>
</template>

<script>

export default {

  mounted() {
    const animations = document.querySelectorAll('.animation');

    this.observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.intersectionRatio > 0) {
          this.imageLoaded[entry.target.id] = true;
          this.imageSeenOnce[entry.target.id] = true;
        } else {
          if (this.imageSeenOnce[entry.target.id] === true){
            return;
          }
          this.imageLoaded[entry.target.id] = false;
        }
      });
    });

    animations.forEach(image => {
      this.observer.observe(image);
    });
  },
  data(){
    return {
      run: true,
      scrollPosition: 0,
      observer: null,
      imageLoaded:{
        "image-1": true,//initialy true so that obsever can observe
        "image-2": true,
        "image-3": true,
        "image-4": true,
        "image-5": true,
      },
      imageSeenOnce:{
        "image-1": false,
        "image-2": false,
        "image-3": false,
        "image-4": false,
        "image-5": false,
      },
      imageRunner:{
        "image-1": true,
        "image-2": true,
        "image-3": true,
        "image-4": true,
        "image-5": true,
      }
    }
  },
  methods:{
    runAgain(imageId){
      this.imageRunner[imageId] = !this.imageRunner[imageId];
      setTimeout(()=>{
        this.imageRunner[imageId] = !this.imageRunner[imageId];
      },20);
    },
  }
}
</script>

<style lang="scss">
@import './assets/reset';
html { margin-left: calc(100vw - 100%); } //scrollbar flicker hack
body{
  font-family: Arial, Helvetica, sans-serif;
  margin: 40px 0;
}

#app{
  display: flex;
  align-items: center;
  flex-direction: column;
}

#app svg{
  width: 300px;
}
h1{
  text-align: center;
  font-size: 30px;
  line-height: 45px;
}
h2{
  text-align: center;
}
p{
  width: 400px;
  line-height: 20px;
  padding: 10px 0;
}
pre code{
  font-family: "Lucida Console", Monaco, monospace;
  font-size: 12px;
  max-width: 740px;
}
pre{
  padding: 10px;
  margin: 20px 0;
  background-color:#ded;
  border-radius: 20px;
}
button{
  margin: 5px 0;
  font-size: 20px;
  border: 2px solid;
  border-radius: 5px;
  cursor: pointer;
}



.draw[data-run=true]{
  stroke-dasharray: 2000;
  stroke-dashoffset: 2000;
  animation: draw 5s linear forwards;
}
@keyframes draw {
  to {
    stroke-dashoffset: 0;
  }
}
.un-draw[data-run=true]{
  stroke-dasharray: 2000;
  stroke-dashoffset: 0;
  animation: un-draw 5s linear forwards;
}
@keyframes un-draw {
  to {
    stroke-dashoffset: -2000;
  }
}
.show-after[data-run=true]{
  animation: fade-in 5s linear forwards;
}
@keyframes fade-in {
    0% { opacity: 0; }
    50% { opacity: 0; }
    60%   { opacity: 1; }
}

</style>

