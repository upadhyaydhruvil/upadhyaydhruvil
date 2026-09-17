<p align="center">
  <img src="./git.png" width="100%" />
</p>
<p align="center">

<a href="https://www.linkedin.com/in/upadhyaydhruvil/">
  <img src="https://img.shields.io/badge/LINKEDIN-000000?style=for-the-badge&logo=linkedin&logoColor=white" />
</a>

<a href="mailto:dhruvilu2@gmail.com">
  <img src="https://img.shields.io/badge/GMAIL-000000?style=for-the-badge&logo=gmail&logoColor=white" />
</a>

<a href="https://x.com/oficialdhruvil">
  <img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" />
</a>

<a href="https://www.instagram.com/upadhyay_dhruvil?stkn=MWR1eG5ua2IzeWdyNA==">
  <img src="https://img.shields.io/badge/INSTAGRAM-000000?style=for-the-badge&logo=instagram&logoColor=white" />
</a>

</p>
<h2>⚡ ABOUT ME</h2>

<table>
<tr>
<td width="60%" valign="top">

<h3>👨‍💻 Who Am I?</h3>

<samp>
Artificial Intelligence And Machine Learning Student | Passionate About Machine Learning, Web Development
</samp>



<b>🧠 Interests</b>

<br><br>

<samp>
• Artificial Intelligence & Machine Learning<br>
• Deep Learning & Generative AI<br>
• Computer Vision<br>
• RAG & Large Language Models<br>
• Full-Stack Development
</samp>

</td>

<td width="40%" align="center">

<img src="./your-image.png" width="300px">

</td>
</tr>
</table>
<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&width=435&lines=The+five+boxing+wizards+jump+quickly;How+vexingly+quick+daft+zebras+jump;Quick+fox+jumps+nightly+above+wizard;Sphinx+of+black+quartz%2C+judge+my+vow;Waltz%2C+bad+nymph%2C+for+quick+jigs+vex" alt="Typing SVG" /></a>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Machine Learning Code Face Portrait</title>
  <style>
    body {
      background-color: #0d1117;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      font-family: monospace;
    }
    canvas {
      box-shadow: 0 0 20px rgba(0,255,136,0.2);
    }
  </style>
</head>
<body>

<canvas id="portraitCanvas"></canvas>

<script>
  // Replace with your image file path or URL
  const IMAGE_SRC = 'WhatsApp Image 2026-08-13 at 3.56.19 PM.jpeg';

  const mlCode = `
import torch
import torch.nn as nn
import torch.optim as optim

class FaceFeatureExtractor(nn.Module):
    def __init__(self):
        super().__init__()
        self.conv1 = nn.Conv2d(3, 64, kernel_size=3, padding=1)
        self.relu = nn.ReLU()
        self.pool = nn.MaxPool2d(2, 2)
        self.fc1 = nn.Linear(64 * 16 * 16, 128)
        self.fc2 = nn.Linear(128, 2)

    def forward(self, x):
        x = self.pool(self.relu(self.conv1(x)))
        x = x.view(x.size(0), -1)
        x = self.relu(self.fc1(x))
        return self.fc2(x)

model = FaceFeatureExtractor()
optimizer = optim.Adam(model.parameters(), lr=0.001)
criterion = nn.CrossEntropyLoss()
loss = criterion(model(inputs), targets)
loss.backward()
optimizer.step()
  `.trim().replace(/\s+/g, ' '); // Clean code into a continuous stream

  const img = new Image();
  img.crossOrigin = "anonymous";
  img.src = IMAGE_SRC;

  img.onload = () => {
    const canvas = document.getElementById('portraitCanvas');
    const ctx = canvas.getContext('2d');

    // Canvas dimensions matched to image aspect ratio
    const maxWidth = 800;
    const scale = maxWidth / img.width;
    canvas.width = maxWidth;
    canvas.height = img.height * scale;

    // Off-screen canvas to process pixels
    const tempCanvas = document.createElement('canvas');
    tempCanvas.width = canvas.width;
    tempCanvas.height = canvas.height;
    const tempCtx = tempCanvas.getContext('2d');

    // Draw full image scaled
    tempCtx.drawImage(img, 0, 0, canvas.width, canvas.height);
    const imgData = tempCtx.getImageData(0, 0, canvas.width, canvas.height);
    const pixels = imgData.data;

    // Dark background
    ctx.fillStyle = "#0d1117";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Font settings for code overlay
    const fontSize = 8;
    ctx.font = `bold ${fontSize}px Courier New, monospace`;

    let charIndex = 0;

    // Loop through grid points
    for (let y = 0; y < canvas.height; y += fontSize) {
      for (let x = 0; x < canvas.width; x += fontSize * 0.6) {
        
        // Pixel color check
        const pixelX = Math.floor(x);
        const pixelY = Math.floor(y);
        const index = (pixelY * canvas.width + pixelX) * 4;

        const r = pixels[index];
        const g = pixels[index + 1];
        const b = pixels[index + 2];
        const alpha = pixels[index + 3];

        // 1. Skip transparent background
        if (alpha < 50) continue;

        // 2. Crop out blue clothing (Face only filter)
        // Checks if blue channel significantly dominates red channel (typical for blue shirt)
        const isClothing = (b > r + 20) && (b > g);
        // Also crop out lower 45% of image if it contains clothes
        const isLowerBody = y > canvas.height * 0.52 && isClothing;

        if (isLowerBody) continue;

        // Pick next code character
        const char = mlCode[charIndex % mlCode.length];
        charIndex++;

        // Render color matching skin tones / facial highlights
        ctx.fillStyle = `rgb(${r}, ${g}, ${b})`;
        ctx.fillText(char, x, y);
      }
    }
  };
</script>

</body>
</html>
<h3 align="center">A passionate frontend developer from India</h3>

<p align="left"> <img src="https://komarev.com/ghpvc/?username=upadhyaydhruvil&label=Profile%20views&color=0e75b6&style=flat" alt="upadhyaydhruvil" /> </p>

<p align="left"> <a href="https://github.com/ryo-ma/github-profile-trophy"><img src="https://github-profile-trophy.vercel.app/?username=upadhyaydhruvil" alt="upadhyaydhruvil" /></a> </p>

<h3 align="left">Connect with me:</h3>
<p align="left">
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://aws.amazon.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" alt="aws" width="40" height="40"/> </a> <a href="https://www.cprogramming.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="c" width="40" height="40"/> </a> <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> <a href="https://www.djangoproject.com/" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/django.svg" alt="django" width="40" height="40"/> </a> <a href="https://www.figma.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma" width="40" height="40"/> </a> <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a> <a href="https://www.java.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="40" height="40"/> </a> <a href="https://www.mongodb.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb" width="40" height="40"/> </a> <a href="https://www.mysql.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="40" height="40"/> </a> <a href="https://nodejs.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs" width="40" height="40"/> </a> <a href="https://opencv.org/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/opencv/opencv-icon.svg" alt="opencv" width="40" height="40"/> </a> <a href="https://pandas.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/pandas/pandas-original.svg" alt="pandas" width="40" height="40"/> </a> <a href="https://www.php.net" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/php/php-original.svg" alt="php" width="40" height="40"/> </a> <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> <a href="https://pytorch.org/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/pytorch/pytorch-icon.svg" alt="pytorch" width="40" height="40"/> </a> <a href="https://reactjs.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="react" width="40" height="40"/> </a> <a href="https://scikit-learn.org/" target="_blank" rel="noreferrer"> <img src="https://upload.wikimedia.org/wikipedia/commons/0/05/Scikit_learn_logo_small.svg" alt="scikit_learn" width="40" height="40"/> </a> <a href="https://seaborn.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://seaborn.pydata.org/_images/logo-mark-lightbg.svg" alt="seaborn" width="40" height="40"/> </a> <a href="https://www.tensorflow.org" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/tensorflow/tensorflow-icon.svg" alt="tensorflow" width="40" height="40"/> </a> </p>

<p><img align="left" src="https://github-readme-stats.vercel.app/api/top-langs?username=upadhyaydhruvil&show_icons=true&locale=en&layout=compact" alt="upadhyaydhruvil" /></p>

<p>&nbsp;<img align="center" src="https://github-readme-stats.vercel.app/api?username=upadhyaydhruvil&show_icons=true&locale=en" alt="upadhyaydhruvil" /></p>

<p><img align="center" src="https://github-readme-streak-stats.herokuapp.com/?user=upadhyaydhruvil&" alt="upadhyaydhruvil" /></p>
