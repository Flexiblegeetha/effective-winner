# effective-winner
My first repository on GitHub.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <link href="toll1.png" rel="icon" sizes="16*16">
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 0px;
      margin-right: 10vh;
      height: 100vh;
      padding-right: 10px;
      align-items: center;
      border-radius: 8px;
      justify-content: center;
      background: radial-gradient(circle,  #3498db, #2ecc71);
    }
  
    #toll-container {
      max-width: 600px;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 5px;
      background: rgba(255, 255, 255, 0.8); /* Set a semi-transparent white background */
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
   label {
      display: block;
      margin-bottom: 5px;
    }
    input, select, button {
      width: 100%;
      padding: 10px;
      box-sizing: border-box;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 3px;
      font-size: 16px;
    }
    button {
      background-color: #2ecc71;
      color: #fff;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #27ae60;
    }

    #result {
      font-size: 18px;
      font-weight: bold;
      color: #2c3e50;
    }
    @media (max-width: 400px) {
      #toll-container {
        max-width: 50%;
      }
      .option {
        margin-bottom: 10px;
      }
    body p{
      text-align: center;
      font-size: 20px;
      padding: 50px;
      color: aliceblue;
      cursor: pointer;
      font-style: Arial, sans-serif;
    }
    body marquee{
      font-size: 40px;
      font-weight: bolder;
      color: #2c4050;
      text-decoration: solid;
      text-decoration-color: whitesmoke;
      cursor: pointer;

    }
  
  </style>
  <title>Toll Calculator</title>
</head>
<body>

  <div id="toll-container">
    <h2>Toll Calculator</h2>

    <div class="option">
      <label for="distance">Enter distance (in miles):</label>
      <input type="number" id="distance" min="0" value="0">
    </div>

    <div class="option">
      <label for="vehicle-type">Select vehicle type:</label>
      <select id="vehicle-type">
        <option value="car">Car</option>
        <option value="truck">Truck</option>
        <option value="motorcycle">Motorcycle</option>
      </select>
    </div>

    <button onclick="calculateToll()">Calculate Toll</button>

    <div id="result"></div>
  </div>

  <script>
    function calculateToll() {
      const distance = parseFloat(document.getElementById('distance').value);
      const vehicleType = document.getElementById('vehicle-type').value;

      if (isNaN(distance) || distance < 0) {
        alert('Please enter a valid distance.');
        return;
      }

      let tollRate;

      switch (vehicleType) {
        case 'car':
          tollRate = 0.1;
          break;
        case 'truck':
          tollRate = 0.2;
          break;
        case 'motorcycle':
          tollRate = 0.05;
          break;
        default:
          alert('Invalid vehicle type.');
          return;
      }

      const tollAmount = distance * tollRate;

      const resultContainer = document.getElementById('result');
      resultContainer.innerHTML = `<p>Toll Amount: $${tollAmount.toFixed(2)}</p>`;
    }
  </script>
  <marquee behavior="" direction="left to right">Welcome to our Toll Free webpage</marquee>

</body>
</html>

