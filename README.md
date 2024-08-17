-<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>HTML</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      background-color: black;
    }

    .kuula-embed-container {
      width: 100vw;
      height: 100vh;
      position: relative;
      overflow: hidden;
      background-color: black;
    }

    .kuula-embed-container iframe {
      width: 100%;
      height: calc(100% + 50px);
      border: none;
      position: absolute;
      top: -50px;
      left: 0;
    }

    .blur-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: rgba(0, 0, 0, 0.2); /* More transparent */
      backdrop-filter: blur(10px);
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 3rem;
      text-align: center;
      z-index: 9999;
      cursor: pointer;
      transition: opacity 0.3s ease;
    }

    .blur-overlay.hidden {
      opacity: 0;
      pointer-events: none;
    }

    .header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: rgba(255, 255, 255, 0.1); /* More transparent white */
      color: black;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0 10px;
      transition: transform 0.3s ease;
      transform: translateY(-100%);
    }

    .header.visible {
      transform: translateY(0);
    }

    .header .logo {
      font-size: 1.2rem; /* Adjusted for better fit */
    }

    .header .nav {
      display: flex;
      gap: 10px; /* Adjusted gap */
      align-items: center;
      padding-right: 20px;
    }

    .header .nav a {
      color: black; /* Updated to match header background */
      text-decoration: none;
      font-size: 0.9rem; /* Reduced font size for better fit */
    }

    .header .dropdown {
      position: relative;
      display: flex;
      align-items: center;
      cursor: pointer;
    }

    .header .dropdown .dots {
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .header .dropdown .dots div {
      width: 4px; /* Size of the dots */
      height: 4px;
      background: black;
      border-radius: 50%;
      margin: 1px 0; /* Space between dots */
    }

    .header .dropdown-content {
      display: none;
      position: absolute;
      top: 100%; /* Position below the dots */
      right: 0;
      background: white;
      color: black;
      border: 1px solid #ccc;
      border-radius: 4px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
      z-index: 1000;
      padding: 5px 0; /* Adjusted padding */
      font-size: 0.8rem; /* Reduced font size */
      min-width: 120px; /* Adjust width as needed */
    }

    .header .dropdown:hover .dropdown-content {
      display: block;
    }

    .header .dropdown-content a {
      display: block;
      padding: 5px 10px; /* Adjusted padding */
      text-decoration: none;
      color: black;
    }

    .header .dropdown-content a:hover {
      background: #f0f0f0;
    }
  </style>
</head>
<body>
  <!-- Project -->
  <div class="kuula-embed-container">
    <script src="https://static.kuula.io/embed.js" data-kuula="https://kuula.co/share/NrQ27?logo=1&info=1&fs=1&vr=0&zoom=1&sd=1&autorotate=0.17&thumbs=1&inst=0" data-width="1280px" data-height="900px"></script>
  </div>

  <!-- Overlay -->
  <div class="blur-overlay" id="overlay">Ayurveda</div>

  <!-- Header -->
  <div class="header" id="header">
    <div class="logo">Ayurveda</div>
    <div class="nav">
      <a href="#">Home</a>
      <a href="#">Contact</a>
      <a href="#">Help</a>
      <div class="dropdown">
        <div class="dots">
          <div></div>
          <div></div>
          <div></div>
        </div>
        <div class="dropdown-content">
          <a href="#">Filter 1</a>
          <a href="#">Filter 2</a>
          <a href="#">Filter 3</a>
        </div>
      </div>
    </div>
  </div>
 
  <script>
    document.getElementById('overlay').addEventListener('click', function() {
      this.classList.add('hidden');
      document.getElementById('header').classList.add('visible');
    });
  </script>
</body>
</html>
pp
