# DAY_028 | Interactive Grid Gallery with GSAP Animation

## Project Overview

For **DAY_028** of my daily code challenge series, I created an **interactive grid gallery** using **HTML**, **CSS**, **JavaScript**, and **GSAP**. This gallery features a dynamic grid layout with seamless zoom animations, smooth dragging functionality, and elegant hover effects. The project demonstrates advanced DOM manipulation, GSAP animations, and responsive design principles to create an engaging, interactive image viewing experience.

---

## Preview

![DAY_028_1](./assets/DAY_028_1.gif)

## Inspiration

This project emerged from my fascination with creating engaging ways to display large image collections. I wanted to combine the efficiency of a grid layout with smooth, intuitive interactions that make browsing through multiple images feel natural and enjoyable.

---

## Key Features

- **Dynamic Grid Layout**: Displays images in a responsive, organized grid structure with consistent spacing.
- **Smooth Zoom Animations**: GSAP-powered zoom functionality with fluid transitions and animations.
- **Drag Navigation**: Interactive dragging in zoomed state for easy exploration of the gallery.
- **Mixed Media Support**: Seamlessly integrates both static images and GIFs in the gallery.
- **Minimalist UI Controls**: Clean, intuitive zoom controls with visual feedback.
- **Blur Effect Overlays**: Backdrop filters for UI elements.

---

## JavaScript and Animation Details

### JavaScript Libraries Used

1. **GSAP (GreenSock Animation Platform)**:
   - Manages zoom animations, transitions, and drag interactions.
2. **script.js**:
   - Handles gallery initialization, image loading, zoom controls, and drag functionality.

### Grid Gallery Implementation

The gallery creates a dynamic grid of images with smooth loading and initialization animations. Each image is carefully positioned and scaled using GSAP for optimal performance.

#### Key Code for Gallery Creation

```javascript
for (let i = 0; i < totalImages; i++) {
  const img = document.createElement("div");
  img.className = "img";
  
  const imgElement = document.createElement("img");
  imgElement.src = getRandomImageSource();
  imgElement.loading = "lazy";
  
  img.appendChild(imgElement);
  gallery.appendChild(img);
  images.push(img);
}
```

### Zoom and Drag Controls

The zoom functionality combines GSAP animations with precise mouse/touch tracking for a smooth, responsive user experience.

#### Code for Zoom Animation

```javascript
zoomInBtn.addEventListener("click", () => {
  if (isZoomed) return;
  isZoomed = true;
  dragLayer.style.display = "block";

  images.forEach((img) => {
    const rect = img.getBoundingClientRect();
    const centerX = window.innerWidth / 2;
    const centerY = window.innerHeight / 2;
    const distX = (rect.left + rect.width / 2 - centerX) / 100;
    const distY = (rect.top + rect.height / 2 - centerY) / 100;

    gsap.to(img, {
      x: distX * 1200,
      y: distY * 600,
      scale: 5,
      duration: 2.5,
      ease: "power4.inOut",
    });
  });
});
```

---

## How to Run

1. **Clone the repository**:
   ```bash
   git clone https://github.com/thounny/DAY_028.git
   ```

2. **Navigate to the project directory**:
   ```bash
   cd DAY_028
   ```

3. **Open the `index.html` file** in your browser, or use a local development server like **Live Server** in VSCode.

---

## Project Structure

```bash
DAY_028/
│
├── assets/ a lot of images
├── fonts/
├── index.html
├── script.js
├── styles.css
```

---

## Technologies Used

- **HTML5**: Provides the structural foundation for the gallery layout.
- **CSS3**: Handles styling, grid layout, and visual effects.
- **JavaScript (ES6)**: Manages gallery creation, interactions, and dynamic content loading.
- **GSAP (GreenSock Animation Platform)**: Powers the smooth animations, zoom effects, and dragging functionality.

---

## Author

![Logo](./assets/index_dwn.gif)

**Thounny Keo**  
Creative Developer & Designer  
Frontend Development Student | Year Up United

---

![miku](./assets/miku.gif)