# My-Art-Gallery
This is the place where the wonderful and beautiful pictures are post 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>My Art Gallery</title>
  <style>
    body {
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 20px;
      color: #333;
    }

    h1 {
      text-align: center;
      color: #fff;
      font-size: 3em;
      margin-bottom: 20px;
    }

    .upload-section {
      text-align: center;
      margin-bottom: 30px;
    }

    input[type="file"] {
      padding: 10px;
      border-radius: 10px;
      background: #fff;
      border: none;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      padding: 10px;
    }

    .gallery img {
      width: 100%;
      height: auto;
      border-radius: 15px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      transition: transform 0.3s;
    }

    .gallery img:hover {
      transform: scale(1.05);
    }
  </style>
</head>
<body>
  <h1>My Art Gallery</h1>
  <div class="upload-section">
    <input type="file" id="imageUpload" accept="image/*" multiple />
  </div>
  <div class="gallery" id="gallery"></div>

  <script>
    const imageUpload = document.getElementById('imageUpload');
    const gallery = document.getElementById('gallery');

    imageUpload.addEventListener('change', function () {
      const files = Array.from(this.files);

      files.forEach(file => {
        const reader = new FileReader();
        reader.onload = function (e) {
          const img = document.createElement('img');
          img.src = e.target.result;
          gallery.appendChild(img);
        };
        reader.readAsDataURL(file);
      });
    });
  </script>
</body>
</html>
