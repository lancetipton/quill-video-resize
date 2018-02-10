# Resize Iframe Videos in Quill.js

This was the outcome of learning Quill, and at the same time needing videos to be resizeable. Im sure this could be done better as a module, but when I started building it, I started it as a format not knowing what it would turn into. I may eventually move it into a module, but I'm not making any promises. Feel free to fork and knock it out.

## To use:

```javascript

// Import the format
import { Video } from 'path_to_file/quill-video-resize.js'

// register with Quill
Quill.register({ 'formats/video': Video });

// Build the editor
editor = new Quill(editorElem, config);

// You must add the editor to the root element after the editor was created and before the video embed!
quill.root.quill = quill;

// Embed the video into the editor:
let src = 'https://www.youtube.com/embed/o-KdQiObAGM'
editor.insertEmbed(index, 'video', src, 'user');

```

#### You must add the editor to the root element after the editor was created and before the video embed!
```javascript
  
  quill.root.quill = quill;
  // I heard you like quill in your quill, so I added some quill to all the quills!
 ```
 
#### Font Awesome
I'm using font awesome for icons, so they are used for the align buttons. I'll try to remove the dependancy at some point.
