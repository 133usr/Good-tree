# Editing by shane

project is too heavy for low end phone
1. tried removing grass but still heavy and is not being loaded don't know why 
2. Now removing sun
    -removed sun nothing happend
    -removed sunlight nothing happend
3. Removing rotation
    -didn't worked either    

4.  Okay I got it May be the issue is line 417
    if (rotate) update controls 
    the controls keep updating causing heaps. this is it (may be)
    -but no it is not Its still hanging 
    -didn't worked

**THUS I NEED TO ADD ALL THE ABOVE 1 2 3 4 BACK TO THE SCRIPT

5. Making ground smaller
    ****-   okay so I think ground rendering is the issue
            becuase from away it is going smooth in mobile but 
            when I zoom in to the ground I stucks
            so I got it ~
            lets find another way of adding ground instead of repeating jpg on screen

            - removing ground
            - still same
            - removing backgroun of clouds
            - still same

*********** I dnt knw what 
            may be the shaders are the issue
            so I quite its just not happending
            instead I'm going to use the forest project and use some of this projects feature in there

#### HEY HEY HEY !! FINALLY I GOT IT

            -its the renderer.setPixelRatio(window.devicePixelRatio);
            - that's the resolution function 
            - You may divide it by 2; and you are done

            or just put a condition

            
    //I want low end phone to run this on low resolution so
    //let's put if
    if (screen.width < 380 || screen.height < 700) {
        alert('Low Resolution mode!');
        renderer.setPixelRatio(window.devicePixelRatio/2);
        }
    else    {
        alert('Good to go!');
        renderer.setPixelRatio(window.devicePixelRatio);
            }

# case closed shane









# Forests (CMPT 361 Assignment 3 Problem 2 )

This project implements a scene renderer based on three.js. The available options for rendering include trees, grass, soil and sun. Additional features include perspective changing, allowing users to view the rendered scene from different perspectives and zoom in/out for closer views.

## Usage
To run this code locally, a local server is needed. (https://threejs.org/docs/#manual/en/introduction/How-to-run-things-locally)

There are multiple ways to open a server, the easiest way is to run the following command under this directory 
```
python -m SimpleHTTPServer
```
and open the following link in the web browser
```
http://localhost:8000/forest.html
```

## Features
* Rendered trees
* Grass growing out of ground gradually
* Natural lighting and shadows (shadows become more clear as the number of object decreases in the scene)
* Simulating Sun rising and falling
* Ground soil texture
* Skydome

## Animation Usage
* Use mouth to control the viewport
* Use middle button to zoom in and out.


## Acknowledge
* Three.js: https://threejs.org/
* Skydome rendering: https://threejs.org/examples/#webgl_water
* Tree rendering: https://codepen.io/leomanlapera/pen/EWBZLW
* Grass rendering: https://github.com/spacejack/terra
* Shadow modeling for instances: https://discourse.threejs.org/t/shadow-for-instances/7947
* Natural lighting: https://stackoverflow.com/questions/15478093/realistic-lighting-sunlight-with-three-js
* Soil texture: https://www.textures.com/

