<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Image Carousel</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f4f4f9;
    }
    .carousel {
      position: relative;
      width: 80%;
      max-width: 600px;
      overflow: hidden;
      border: 2px solid #ddd;
      border-radius: 10px;
    }
    .carousel img {
      width: 100%;
      display: none;
    }
    .carousel img.active {
      display: block;
    }
    .arrow {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      font-size: 2rem;
      color: #333;
      background: rgba(255, 255, 255, 0.7);
      border: none;
      cursor: pointer;
      padding: 0.5rem;
      z-index: 10;
    }
    .arrow.left {
      left: 10px;
    }
    .arrow.right {
      right: 10px;
    }
  </style>
</head>
<body>
  <div class="carousel">
    <button class="arrow left" onclick="prevImage()">&#8592;</button>
    <img src="https://via.placeholder.com/600x400/FF0000/FFFFFF?text=Image+1" class="active" alt="Image 1">
    <img src="https://via.placeholder.com/600x400/00FF00/FFFFFF?text=Image+2" alt="Image 2">
    <img src="https://via.placeholder.com/600x400/0000FF/FFFFFF?text=Image+3" alt="Image 3">
    <button class="arrow right" onclick="nextImage()">&#8594;</button>
  </div>

  <script>
    let currentIndex = 0;
    const images = document.querySelectorAll('.carousel img');

    function showImage(index) {
      images.forEach((img, i) => {
        img.classList.toggle('active', i === index);
      });
    }

    function nextImage() {
      currentIndex = (currentIndex + 1) % images.length;
      showImage(currentIndex);
    }

    function prevImage() {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
      showImage(currentIndex);
    }
  </script>
</body>
</html>
