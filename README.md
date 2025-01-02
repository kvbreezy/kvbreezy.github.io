<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>API Audio Guide</title>
  <style>
    /* Set up the background photo */
    body, html {
      margin: 0;
      padding: 0;
      height: 100%;
      width: 100%;
    }

    .background {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: url('jiha-moon.jpg'); /* Replace with your image path */
      background-size: cover;
      background-position: center;
      filter: brightness(80%);
    }

    /* Center the text box */
    .content {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      color: white;
      text-align: center;
      font-family: Arial, sans-serif;
      padding: 20px;
      border-radius: 20px;
      background-color: rgba(0, 0, 0, 0.7);
      width: 80%;
      max-width: 600px;
    }

    .content h1 {
      font-size: 3rem;
      margin: 0;
    }

    .content p {
      font-size: 1.2rem;
      margin-top: 10px;
    }

    /* Audio controls at the bottom of the text box */
    .audio-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 20px;
    }

    .play-button, .pause-button {
      background-color: #76c7c0;
      border: none;
      color: white;
      padding: 10px;
      cursor: pointer;
      font-size: 18px;
      border-radius: 50%;
    }

    .play-button {
      display: inline-block;
    }

    .pause-button {
      display: none;
    }

    .progress-bar {
      flex-grow: 1;
      margin-left: 10px;
      margin-right: 10px;
      height: 6px;
      background-color: #555;
      cursor: pointer;
      border-radius: 3px;
      position: relative;
    }

    .progress {
      width: 0;
      height: 100%;
      background-color: #76c7c0;
      border-radius: 3px;
    }

  </style>
</head>
<body>

  <!-- Background Image -->
  <div class="background"></div>

  <!-- Content Box with Text -->
  <div class="content">
    <h1>API Voices</h1>
    <h2>Audio Guide
    <p>You're listening to Dr. Sangmin Lee, Assistant Professor of Art Education.</p>

    <!-- Audio Controls -->
    <div class="audio-controls">
      <button class="play-button">►</button>
      <button class="pause-button">❚❚</button>
      <div class="progress-bar">
        <div class="progress"></div>
      </div>
    </div>
  </div>

  <!-- Audio element -->
  <audio id="audio" src="Sangmin-Lee-English.m4a" preload="auto"></audio>

  <script>
    const audio = document.getElementById('audio');
    const playButton = document.querySelector('.play-button');
    const pauseButton = document.querySelector('.pause-button');
    const progressBar = document.querySelector('.progress-bar');
    const progress = document.querySelector('.progress');

    // Play and pause buttons functionality
    playButton.addEventListener('click', () => {
      audio.play();
      playButton.style.display = 'none';
      pauseButton.style.display = 'inline-block';
    });

    pauseButton.addEventListener('click', () => {
      audio.pause();
      playButton.style.display = 'inline-block';
      pauseButton.style.display = 'none';
    });

    // Update progress bar as audio plays
    audio.addEventListener('timeupdate', () => {
      const progressPercentage = (audio.currentTime / audio.duration) * 100;
      progress.style.width = `${progressPercentage}%`;
    });

    // Seek functionality (click on progress bar)
    progressBar.addEventListener('click', (e) => {
      const clickX = e.offsetX;
      const duration = audio.duration;
      const newTime = (clickX / progressBar.offsetWidth) * duration;
      audio.currentTime = newTime;
    });
  </script>

</body>
</html>
