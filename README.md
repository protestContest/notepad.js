# Notepad.js

This is a simple HTML canvas notepad I made, with Apple Pencil support. The goal
was to be simple and hackable, and provide basic canvas-based notetaking
features like line smoothing and undo/redo.

While Apple Pencil support on the iPad was a primary motivation for this, I'll
note that the results aren't fantastic. Safari reports touch movement on the
canvas in whole CSS pixels, which are larger than the real retina pixels, and
the resulting strokes are fairly jagged. If you find a solution, let me know!

## Demo

<video src="./demo.mp4"></video>

## Usage

To use Notepad.js, simply include the library, and declare one or more canvas
elements as notepads:

```html
<script src="notepad.js"></script>

<canvas data-notepad></canvas>
```

You can pass a JSON object of the image data, too:

```html
<canvas data-notepad="{ strokes: [ ... ] }"></canvas>
```

Image data is saved as a JSON object with this structure:

```json
{
  "strokes": [
    [
      {
        "x": 10,
        "y": 10,
        "force": 0.2
      },
      {
        "x": 20,
        "y": 20,
        "force": 0.2
      },
      {
        "x": 15,
        "y": 25,
        "force": 0.2
      },
      // ... other stroke points
    ],
    // ... other strokes
  ]
}
```

## Future Work

- It would be great if there was some way to get more precise position data from
  the browser's touch events.
- Custom brushes
- Better line smoothing
