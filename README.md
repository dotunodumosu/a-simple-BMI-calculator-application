<html>

<head>
  <title>BMI Calculator</title>
  <script type="text/javascript">
    function computeBMI() {
      //Obtain user inputs
      var height = Number(document.getElementById("height").value);
      var heightunits = document.getElementById("heightunits").value;
      var weight = Number(document.getElementById("weight").value);
      var weightunits = document.getElementById("weightunits").value;
      //Convert all units to metric
      if (heightunits == "inches") height /= 39.3700787;
      if (weightunits == "lb") weight /= 2.20462;
      //Perform calculation
      var BMI = weight / Math.pow(height, 2);
      //Display result of calculation
      document.getElementById("output").innerHTML = Math.round(BMI * 100) / 100;
      if (BMI < 18.5) document.getElementById("comment").innerHTML = "Underweight";
      if (BMI >= 18.5 && BMI <= 25) document.getElementById("comment").innerHTML = "Normal";
      if (BMI >= 25 && BMI <= 30) document.getElementById("comment").innerHTML = "Obese";
      if (BMI > 30) document.getElementById("comment").innerHTML = "Overweight";
    }
    }
  </script>
</head>

<body>
  <h1>Body Mass Index Calculator</h1>
  <p>Enter your height:
    <input type="text" id="height" />
    <select type="multiple" id="heightunits">
                <option value="metres" selected="selected">metres</option>
                <option value="inches">inches</option>
            </select>
  </p>
  <p>Enter your weight:
    <input type="text" id="weight" />
    <select type="multiple" id="weightunits">
                <option value="kg" selected="selected">kilograms</option>
                <option value="lb">pounds</option>
            </select>
  </p>
  <input type="button" value="computeBMI" onclick="computeBMI()" />
  <h1>Your BMI is: <span id="output">?</span></h1>

  <h2>This means you are: value = <span id='comment'></span> </h2>
</body>

</html>
