# MWAD_EX05_image-carousel-in-react
## Date:

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM

Gallery.jsx

```
import React from "react";
import "./gallery.css";

function ImageCarousel({ image }) {
  return (
    <div className="carousel-container">
      <img src={image} alt="Carousel" />
    </div>
  );
}

export default ImageCarousel;

```

Gallery.css
```
.carousel-container {
  width: 700px;
  height: 500px;
  margin: 100px auto;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3);
}

.carousel-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
```

App.jsx
```
import ImageCarousel from "./gallery";
import c1 from "./assets/c1.jpg"; // make sure name matches your image

function App() {
  return (
    <div>
      <h1 style={{ textAlign: "center" }}>My Image Carousel</h1>
      <ImageCarousel image={c1} />
    </div>
  );
}

export default App;

```


## OUTPUT
<img width="1869" height="963" alt="image" src="https://github.com/user-attachments/assets/79a06947-38c6-4023-908f-81721268f159" />



## RESULT
The program for creating Image Carousel using React is executed successfully.
