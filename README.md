<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>NK Sodium Adsorption Ratio (SAR)</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
    input { margin: 5px; padding: 5px; width: 100px; }
    button { padding: 10px 20px; }
  </style>
</head>
<body>
  <h1>NK Sodium Adsorption Ratio (SAR)</h1>
  <p>Powered by Nitesh Kumar</p>
  <input id="ca" type="number" placeholder="Calcium (Ca mg/L)">
  <input id="mg" type="number" placeholder="Magnesium (Mg mg/L)">
  <input id="na" type="number" placeholder="Sodium (Na mg/L)">
  <br>
  <button onclick="calcSAR()">Calculate SAR</button>
  <p id="result"></p>
  <script>
    function calcSAR() {
      let ca = parseFloat(document.getElementById('ca').value) || 0;
      let mg = parseFloat(document.getElementById('mg').value) || 0;
      let na = parseFloat(document.getElementById('na').value) || 0;

      let ca_meq = ca / 20.04;
      let mg_meq = mg / 12.15;
      let na_meq = na / 23;

      let denominator = Math.sqrt((ca_meq + mg_meq) / 2);
      let sar = na_meq / (denominator || 1);
      
      document.getElementById('result').innerText = `SAR: ${sar.toFixed(2)}`;
    }
  </script>
</body>
</html>
