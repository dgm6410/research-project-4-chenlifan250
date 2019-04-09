Project 4
-------------------------------------------------------------

- My Topic: Unity Shader: Sketch Shader

This Shader will draw every object in Sketch style.

![](https://github.com/dgm6410/research-project-4-chenlifan250/raw/master/sketchScene.jpg)

-------------------------------------------------------------

DEMO HERE:
-------------------------------------------------------------
Link of Video: https://youtu.be/SpFSvb3zCec

<video id="video" controls="" preload="none" poster="https://github.com/dgm6410/research-project-4-chenlifan250/raw/master/sketchScene.jpg">
<source id="mp4" src="https://youtu.be/SpFSvb3zCec" type="video/mp4">
</video>

-------------------------------------------------------------

List of Content:
-------------------------------------------------------------
- Source Code with Comments
- Mac and Windows Build
  (https://drive.google.com/drive/folders/1E9-B1vkDdzgLLHBNuOKpohrNHjYCyDyw?usp=sharing)
- Tech Blog 
- Demo(video) 
  (https://youtu.be/SpFSvb3zCec) 

Tech Blog:
-------------------------------------------------------------

### 1. Outline
I use an additional pass before we render the object. In this pass, I only render back surface of the object, so we cull the front.
~~~
Cull Front
~~~

Then, I expand the surface a little bit than the original position, so that it will be a little larger than the front surface. Here I use the normal of each surface, which I used in Project 1(Normal Shader). 
~~~
normal.z = -0.5;    
pos = pos + float4(normalize(normal), 0) * _Outline;
~~~

Then, I render the expended back surface in black as the outline of the object.

### 2.Tone Map
Just as the same technology I use in project 2(Cartoon Shader), Toon Map is the main tech I use in this project. I calculate the color of diffuse reflection for every point and then map the color to a sketch texture this time.

![](https://github.com/dgm6410/research-project-4-chenlifan250/raw/master/SketchMap.JPG)
