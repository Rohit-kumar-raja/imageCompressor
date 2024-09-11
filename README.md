# imageCompressor

## Compress and Resize Multiple Images - README

### Project Overview
This is a simple web application that allows users to upload multiple images, compress them to a target size, and display the compressed images along with their respective sizes. The app compresses images on the client side using HTML5's Canvas API and JavaScript.

### Features
- Users can upload one or more images at a time.
- Each image is resized and compressed to a target size of 100KB.
- Compressed images are displayed on the page with their new file size.
- Works entirely in the browser—no need for a server-side backend.

### Technologies Used
- HTML
- CSS
- JavaScript
- HTML5 Canvas API for image manipulation

### How It Works
1. The user selects one or more image files using the file input element.
2. For each image:
   - It is read into the browser as a `File` object.
   - The image is drawn onto a canvas element.
   - The canvas is resized and the image quality is reduced until it reaches the target file size.
   - The final compressed image is displayed alongside its file size.
3. Compressed images are created using the `Blob` API and displayed as `File` objects.

### How to Use
1. Download or clone this repository to your local machine.
2. Open the `index.html` file in your web browser.
3. Click the "Upload" button to select one or more image files.
4. The selected images will be compressed to the target size (100KB by default) and displayed on the page along with their new sizes.

### Folder Structure
```
root
│
├── index.html     # Main HTML file containing the UI and JavaScript
└── demo.jpg       # Demo image for testing (optional)
```

### Code Explanation

#### HTML
The main structure of the app is built using simple HTML:
- `input` element with `multiple` attribute allows users to select multiple image files.
- An image container (`<div id="imageContainer"></div>`) is used to display compressed images and their sizes.

#### JavaScript
The main functionality is handled in the `<script>` tag:
- **File Input Handling**: 
  - A file input event listener triggers the image compression process when files are selected.
- **Image Compression**:
  - The `compressImageToTargetSize` function processes each file, resizes it, and reduces its quality until the target size (100KB) is achieved.
  - It uses a combination of HTML5 Canvas API for resizing and `toBlob` for converting the canvas back into a compressed image.
- **Display**:
  - After compression, the images and their sizes are dynamically inserted into the `imageContainer`.

### Customization

You can modify the following features based on your requirements:

- **Target Size**: Change the `targetSize` variable to set the desired size limit for compressed images (currently set to 100KB).
  ```javascript
  let targetSize = 100 * 1024; // Change 100 to the size in KB you prefer
  ```
  
- **Image Quality**: You can adjust the initial quality by modifying the `quality` variable in the `compressImageToTargetSize` function.
  ```javascript
  let quality = 0.9; // Initial compression quality (1.0 is best, 0.0 is lowest)
  ```

### Dependencies
There are no external libraries or dependencies needed to run this project. The code runs purely on vanilla JavaScript, HTML, and CSS.

### License
This project is open-source and available under the [MIT License](LICENSE).

---

Enjoy compressing and resizing your images efficiently in the browser with this lightweight and simple tool!
