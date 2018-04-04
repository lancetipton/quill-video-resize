# Resize Iframe Videos in Quill.js

This was the outcome of learning Quill, and at the same time needing videos to be resizeable. Im sure this could be done better as a module, but when I started building it, I started it as a format not knowing what it would turn into. I may eventually move it into a module, but I'm not making any promises. Feel free to fork and knock it out.

## To use:
Include both the JS and CSS files. Then add this to your codes:

```javascript

// Import the format
import { Video } from 'path_to_file/quill-video-resize.js'
require("path_to_file/quill-video-resize.css");

// register with Quill
Quill.register({ 'formats/video': Video });

// Build the editor
quill = new Quill(domElem, config);

// You must add the editor to the root element after the editor was created and before the video embed!
quill.root.quill = quill;

// Embed the video into the editor:
let src = 'https://www.youtube.com/embed/o-KdQiObAGM'
quill.insertEmbed(index, 'video', src, 'user');

```

#### You must add the editor to the root element after the editor was created and before the video embed!
```javascript
  
  quill.root.quill = quill;
  // I heard you like quill in your quill, so I added some quill to all the quills!
```

#### Align Icons
If you have Font Awesome in your project, you can remove these style rules from the included css and it will use the Font Awesome align icons instead
```css
.ql-editor .td-video .td-align-left:after{ 
  content: "\ \21E4"; 
} 
.ql-editor .td-video .td-align-center:after{ 
  content: "\ \2194";
  position: relative;
  left: -2px;
  top: -1px;
} 
.ql-editor .td-video .td-align-right:after{
  content: "\ \21E5"; 
}
```
 
#### React Demo
For an example checkout this [Fork](https://github.com/lancetipton/react-quill-experiment)
 
#### Video Demo
[See It In Action](http://recordit.co/AWHy9FuQfP)
