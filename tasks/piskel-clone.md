| Deadline  | Folder name |
|-----------|-------------|
| 23:59 30.06.2019 | piskel-clone |

# Piskel-clone

## Functional requirements
You need to create simplified clone of the https://www.piskelapp.com/ web-based tool for Spriting and Pixel art.
Overview of features can be found on this playlist: https://www.youtube.com/playlist?list=PLO3K3VFvlU6Akj3W29_nMLZFnwNOVbAzI

### Required functionality
#### Minimal scope
- Canvas size 32x32 / 64 * 64 / 128 * 128 / user defined units
- Tools:
    - Pen. Required size is 1 unit. Other units (2,3,4) are optional.
    - Color select (Primary/Secondary)
    - Paint Bucket 
    - Eraser
- Preview
    - Small animation preview on the top of the right corner 
    - Full screen mode
- Frames
    - Ability to add/delete a frame
    - Ability to reorder a frame via Drag and Drop
    - Ability to duplicate a frame
- Export the final result 
    - to local system in any format (pisket / own / gif / apng)
- User session 
  - current session should be saved and open when use will open the page again


### Full scope
- Tools
  - Canvas size 32x32 units / 64*64 units / 128*128 units
  - Paint all pixels of the same color
  - Stroke (to draw straight lines)
  - Reactangle
  - Circle
  - Move
  - Shape selection
  - Lighten
  - Dithering
- Layers
  - Ability to add/delete a layer
  - Ability to move up/down a layer
  - Ability to duplicate a frame
- Export the final result 
  - upload GIF to giphy using upload api https://developers.giphy.com/docs/
  - in custom piskel
  - own format to filesystem with ability to open it later
  - as apng
  - as gif
- Keyboard shotcuts 
  - all actions should be available
  - modal window to change keyboard shortcuts
- Layers
  - Ability to add/delete a layer
  - Ability to move up/down a layer
  - Ability to duplicate a frame
- Landing page. This page should include the next information:
   - Screenshots
   - Animation examples
   - Implemented functionality overview
   - Link to open the editor
   - Information about the author

## Technical requirements:
1) Browser support: latest version of Google **Chrome**
2) Usage of **JS/ES2015+** or **TypeScript**
3) You can use libraries and frameworks like react/angular/vue/jquery/bootstrap/lodash/wrapper for file formats / api utilisation.
4) Final version of the editor should be **available by link**. The easiest way to realize it is to publish your project on Github pages / google firebase / heroku
5) usage of jest / other tool for writing test. Also need to setup test coverage output in the package json. It needs to test the following code:
   1) pure utils functions
   2) ui components
   3) tools functionality (add pixels, change pixels, add rectangle / circle)
6) need to use browser canvas api to draw frames

### Requirements to the commits, PR, repository
https://github.com/rolling-scopes-school/docs/blob/master/ru/stage2-tasks-requirements.md

### Requirements to the quality of code
- Don't use nested SetTimeout, synchronization of code using timeouts etc. Use promises/async/await where it's possible.
- Don't use magic number instead of named constants.  
  For example, instead of  
  `if (event.keyCode === 32 || event.keyCode === 13) {….}`  
  use  
  `if (event.keyCode === KeyboardEvent.SPACE || key === KeyboardEvent.ENTER ) {….}` etc.
- Don't use functions, that have more than 40 lines of code (excluding variable declarations).
- Minimal use of ternary operators.
- Use pure functions where it's possible. If you haven't heard this term before, you can start acquaintance [here](https://medium.com/@jamesjefferyuk/javascript-what-are-pure-functions-4d4d5392d49c) or [here](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-pure-function-d1c076bec976) 
- Use meaningful names for variables. Avoid single characters for variable names (i,n,j,d etc.), abstract or common names (obj, arr, num, item1 etc.)
- Use the eslint with airbnb for all js code 

### Project structure. Organization of files and folders(example):
Using of webpack is mandatory! Components directories should include all needed resources and styles. For example, by removing folder `modal-dialog` all styles related to this dialog will be removed as well.
    
    dist
    src
    ├── components                
    │   ├── loading
    │   ├── modal-dialog
    │   ├── frames-list
    │   ├── layers-list
    ├── screens
    │   ├── canvas
    │   │   ├── images
    │   │   ├── index.html       # template
    │   │   ├── index.scss       # styles
    │   │   ├── index.js         # logic
    │   ├── preview
    │   ├── export
    ├── app.js                   # main entry point.
    webpack.config.js
    README.md

Notes for webpack usage: 
- There is no sense to put your code inside of Immediately-invoked Function Expression.
- There is no sense to apply 'use strict' mode.

## Delivery process and score criteria
### Delivery process:
- You'll have up to **15 min** to present your project.
- Other students may attend / ask you questions.
- It can be offline or online depending on the location/opportunities of the reviewers.
- The final scoring and reviewing will be performed **NOT** by your mentor from stage#2. The list "*student - reviewer*" will be published after the deadline.

### Score criteria:

Basic (100)  + Normal (300) + Extra (130) + Impossible (70) - **+600**

#### Basic scope 

Max - **+100**

- [ ] Landing Page is presented: **+20 points.**
- [ ] Usage of Webpack and required project structure: **+10 points.**
- [ ] Custom canvas size (32/64/128) - **+10**
- [ ] Tools (max - **+20**) 
  - Pen. Required size is 1 unit. Other units (2,3,4) are optional.(**+5**)
  - Color select (rimary/Secondary) (**+5**)
  - Paint Bucket  (**+5**)
  - Eraser (**+5**)
- [ ] Preview **+20**
- [ ] Frame management **+10**
- Unit tests
  - [ ] setup jest + cover couple functions with tests (utils / pure functions for example) **+10**

### Normal scope 

Max - **+300**
- Tools (max - **+130**)
  - [ ] Paint all pixels of the same color **+10**
  - [ ] Stroke (to draw straight lines) **+10**
  - [ ] Move **+10**
  - [ ] Reactangle **+10**
  - [ ] Circle **+10**
  - [ ] Shape selection **+10**
  - [ ] Lighten **+10**
  - [ ] Dithering **+10**
  - [ ] Other 5 custom tools (**+10** for each)
- Layers (max - **+30**)
  - [ ] Add/delete a layer **+10**
  - [ ] Move up/down a layer **+10**
  - [ ] Duplicate a frame **+10**
- [ ] Show cursor coordinates / canvas size **+10**
- Keyboard shotcuts (max - **+20**)
  - [ ] All actions should be available **+10**
  - [ ] Modal window to change keyboard shortcuts **+10**
- [ ] Export gif to local filesystem **+10**
- Unit tests (max - **110**)
  - [ ] achieve good coverage  **+1** for every percent of coverage (max - **+100**)
  - [ ] achive 25% of coverage **+10**


### Extra (additional) scope
Max - **+130**
- [ ] Login with one oauth provides from Google / Github / Facebook / VK (**+20**)
- Export the final result (max - **+100**)
    - [ ] Piskel format to file system **+10**
    - [ ] Own format to file system **+10**
    - [ ] As apng to file system **+15**
    - [ ] As gif to file system **+15**
    - [ ] Upload GIF to giphy **+10**
    - [ ] Upload any file to google drive **+30**
- Unit tests
  - [ ] achieve at least 40% coverage (for utils / pure functions) **+10**

### Impossible scope

Max - **+70**

- Unit tests
  - [ ] achieve at least 60% coverage (for utils / pure functions) **+10**
- [ ] Full compatibility with original export (.piskel) **+60**


### Fines
- [ ] Violation of the general requirements to the tasks performing in RSSchool stage#2 or the quality of the code: **-50 points** and more depending on the decision of the mentor. 

#### Useful links:
1) http://www.williammalone.com/articles/html5-canvas-javascript-paint-bucket-tool/

### Lecture materials from @davojta with analysis of the common mistakes, which appear during the task performing 
- https://github.com/rolling-scopes-school/lectures/blob/master/lectures/refactoring.md
