# effective-winner
My first repository on GitHub.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 20px;
    }

    #toll-container {
      max-width: 400px;
      margin: auto;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .option {
      margin-bottom: 10px;
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

</body>
</html>

