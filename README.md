# Campus
HTML Code (face recognition UI)*

```html
<!DOCTYPE html>
<html>
<head>
  <title>Face Recognition</title>
  <script defer src="https://unpkg.com/face-api.js"></script>
  <style>
    video { width: 500px; border: 1px solid #333; }
    canvas { position: absolute; top: 0; left: 0; }
  </style>
</head>
<body>
  <h2>Face Recognition Demo</h2>
  <video id="video" autoplay muted></video>
  <script>
    // Load models and start video
    Promise.all([
      faceapi.nets.tinyFaceDetector.loadFromUri('/models'),
      faceapi.nets.faceLandmark68Net.loadFromUri('/models'),
      faceapi.nets.faceRecognitionNet.loadFromUri('/models')
    ]).then(startVideo);

    function startVideo() {
      navigator.mediaDevices.getUserMedia({ video: {} })
        .then(stream => {
          document.getElementById('video').srcObject = stream;
        });
    }

    const video = document.getElementById('video');

icon in html code
