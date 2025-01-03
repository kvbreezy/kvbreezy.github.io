<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Webpage with Background and Textbox</title>
  <style>
    /* Make the whole page fill the screen */
    body, html {
      margin: 0;
      padding: 0;
      height: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      background-image: url(jiha-moon.jpg); 
      background-size: cover;
      background-position: center;
    }

    .textbox {
      width: 300px;
      padding: 20px;
      font-size: 16px;
      text-align: center;
      border-radius: 10px;
      border: 2px solid #fff;
      background-color: rgba(255, 255, 255, 0.7); /* 70% opacity */
    }
  </style>
</head>
<body>

  <div class="textbox">
    <input type="text" placeholder="Enter text here" />
  </div>

</body>
</html>
