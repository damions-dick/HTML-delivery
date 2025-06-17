<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Track Your Package – IberLogix</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #eef2f5;
      padding: 40px;
    }
    .container {
      max-width: 600px;
      margin: auto;
      background: #fff;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }
    h1 {
      color: #d81b60;
    }
    input, button {
      width: 100%;
      padding: 12px;
      margin: 10px 0;
      font-size: 16px;
      border-radius: 6px;
      border: 1px solid #ccc;
    }
    button {
      background-color: #d81b60;
      color: white;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background-color: #c2185b;
    }
    .status-box {
      background: #fce4ec;
      border-left: 4px solid #d81b60;
      padding: 15px;
      margin-top: 20px;
      display: none;
      white-space: pre-wrap;
    }
    .map {
      margin-top: 20px;
      display: none;
    }
    .map img {
      width: 100%;
      border-radius: 10px;
      border: 2px solid #ccc;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>IberLogix Package Tracking</h1>
    <p>Enter your tracking number below:</p>
    <input type="text" id="trackingNumber" placeholder="e.g. VB6UPQ0WLM">
    <button onclick="track()">Track Package</button>

    <div class="status-box" id="trackingStatus"></div>
    <div class="map" id="mapBox">
      <p><strong>Live Location: Near Madrid, Spain</strong></p>
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/90/Gran_V%C3%ADa_-_Madrid_%28cropped%29.jpg/800px-Gran_V%C3%ADa_-_Madrid_%28cropped%29.jpg" alt="Map showing Madrid location">
    </div>
  </div>

  <script>
    function track() {
      const input = document.getElementById('trackingNumber').value.trim();
      const statusBox = document.getElementById('trackingStatus');
      const mapBox = document.getElementById('mapBox');

      if (input === "VB6UPQ0WLM") {
        statusBox.innerText = `Tracking Number: VB6UPQ0WLM\nStatus: Out for delivery – Madrid, Spain\nEstimated delivery: Today before 17:00`;
        mapBox.style.display = "block";
      } else if (input === "") {
        statusBox.innerText = "⚠️ Please enter a tracking number.";
        mapBox.style.display = "none";
      } else {
        statusBox.innerText = "❌ Invalid tracking number. Please check and try again.";
        mapBox.style.display = "none";
      }

      statusBox.style.display = "block";
    }
  </script>
</body>
</html>
