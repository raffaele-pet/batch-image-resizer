# Batch Image Resizer

A browser-based workspace for uploading, arranging, resizing, and exporting multiple images.

## Features

- upload or drag and drop multiple images
- choose common aspect ratios or preserve the original ratio
- resize, position, fill, fit, and center each image
- fill empty workspace margins by extending the image's edge pixels
- snap image edges to the workspace borders while moving or scaling
- undo up to 50 edits, including image removal, with Ctrl+Z (Cmd+Z on Mac) or the Undo button
- select adaptive output sizing or a fixed long edge up to 8K
- export as JPG, PNG, or WebP
- preserve original file names or use a numbered sequence
- download all processed images together in a ZIP archive

## Open the app

Use the published version at:

https://raffaele-pet.github.io/batch-image-resizer/

Images are processed locally in the browser and are not uploaded to a server.

## Editing controls

Drag an image to position it, or drag a corner handle to scale it. Edges snap when
they are within 10 screen pixels of the corresponding workspace border, at any
view zoom. Scaling preserves proportions and keeps the opposite corner fixed.
Hold Alt to scale from the center, or Shift to scale width and height independently;
snapping also works with these modifiers.

Click **Edge pixel**, next to Fill and Fit, to fill the space outside the current
image by stretching its outermost pixel rows and columns, including the corners.
The image keeps its position and scale. This toggle applies per image, updates
as you move or scale it, and is included in JPG, PNG, and WebP exports. Click it
again to restore the usual background. Transparency inside the source image is
preserved.

Use Ctrl+Z (Cmd+Z on Mac) or **Undo** to reverse uploads, removals, moves, scaling,
Fill, Fit, Edge pixel, Center, and workspace aspect ratio or output size changes. Each drag
counts as one edit. Restoring a removed image also restores its position in the
list and its composition. Undo history lasts for the current page session and
keeps the latest 50 edits. Text fields retain their normal text undo behavior.

## Tests

Run the editor regression tests with Node.js (no dependencies required):

```sh
node --test tests/editor.test.cjs
```
