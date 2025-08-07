<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simple Antivirus UI</title>
  <style>
    
body {
  font-family: Arial, sans-serif;
  background-color: #f2f2f2;
  color: #333;
  margin: 0;
  padding: 20px;
}

.container {
  max-width: 600px;
  margin: auto;
  background: white;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

h1 {
  color: #007BFF;
  text-align: center;
}

.status {
  font-weight: bold;
  color: green;
}

.buttons {
  display: flex;
  justify-content: space-around;
  margin: 20px 0;
}

button {
  padding: 10px 20px;
  background: #007BFF;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background: #0056b3;
}

.log {
  background: #f9f9f9;
  border: 1px solid #ddd;
  padding: 15px;
  border-radius: 5px;
  max-height: 200px;
  overflow-y: auto;
}

.log ul {
  list-style: none;
  padding: 0;
}

.log li {
  margin: 5px 0;
  font-size: 14px;
}

  </style>
</head>
<body>
  <div class="container">
    <h1>Antivirus Scanner</h1>
    <p>Status: <span class="status">Idle</span></p>
    <div class="buttons">
      <button onclick="fakeScan()">Start Scan</button>
      <button>Update</button>
      <button>Settings</button>
    </div>
    <div class="log">
      <h2>Scan Log</h2>
      <ul id="scan-log"></ul>
    </div>
  </div>

  <script>
    function fakeScan() {
      document.querySelector(".status").textContent = "Scanning...";
      const log = document.getElementById("scan-log");
      log.innerHTML = "";
      const fakeFiles = ["C:/Windows/System32", "C:/Program Files", "D:/Games", "C:/Users/You/Documents"];
      fakeFiles.forEach((file, index) => {
        setTimeout(() => {
          const li = document.createElement("li");
          li.textContent = `Scanned: ${file} - No Threats Found`;
          log.appendChild(li);
          if (index === fakeFiles.length - 1) {
            document.querySelector(".status").textContent = "Scan Complete";
          }
        }, index * 1000);
      });
    }
  </script>
</body>
</html>










