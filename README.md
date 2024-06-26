<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BMI Calculator</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #0d47a1; /* Dark blue background for the first layer */
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
    }
    .container {
        background-color: #f5f5f5; /* Light gray container background */
        border-radius: 20px; /* Rounded corners */
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3); /* Darker shadow effect */
        padding: 40px;
        width: 400px;
        text-align: center;
        background-image: linear-gradient(to bottom right, #ffffff, #f5f5f5); /* Subtle gradient */
    }
    h1 {
        margin-top: 0;
        color: #333; /* Dark text color */
    }
    form {
        margin-top: 20px;
    }
    label {
        display: block;
        margin-bottom: 5px;
        color: #333; /* Dark text color */
        font-weight: bold;
    }
    input[type="number"], input[type="submit"] {
        width: calc(100% - 22px);
        padding: 10px;
        margin-bottom: 20px;
        box-sizing: border-box;
        border: 1px solid #ccc;
        border-radius: 5px;
    }
    input[type="submit"] {
        background-color: #4CAF50; /* Green button */
        color: white;
        border: none;
        cursor: pointer;
    }
    input[type="submit"]:hover {
        background-color: #45a049; /* Darker green on hover */
    }
    #result {
        margin-top: 20px;
        text-align: center;
    }
    #result span {
        font-size: 24px;
        color: #333; /* Dark text color */
        font-weight: bold;
        animation: shake 0.8s;
    }

    @keyframes shake {
        0% { transform: translateX(0); }
        10% { transform: translateX(-10px); }
        20% { transform: translateX(10px); }
        30% { transform: translateX(-10px); }
        40% { transform: translateX(10px); }
        50% { transform: translateX(-10px); }
        60% { transform: translateX(10px); }
        70% { transform: translateX(-10px); }
        80% { transform: translateX(10px); }
        90% { transform: translateX(-10px); }
        100% { transform: translateX(0); }
    }
</style>
</head>
<body>

<div class="container">
    <h1>BMI Calculator</h1>
    <form id="bmiForm">
        <label for="height">Height (cm):</label>
        <input type="number" id="height" name="height" required>

        <label for="weight">Weight (kg):</label>
        <input type="number" id="weight" name="weight" required>

        <input type="submit" value="Calculate">
    </form>

    <div id="result"></div>
</div>

<script>
    document.getElementById('bmiForm').addEventListener('submit', function(e) {
        e.preventDefault();
        
        var height = parseFloat(document.getElementById('height').value);
        var weight = parseFloat(document.getElementById('weight').value);

        var bmi = calculateBMI(height, weight);
        
        document.getElementById('result').innerHTML = "<h2>Your BMI is: <span>" + bmi.toFixed(2) + "</span></h2>";
    });

    function calculateBMI(height, weight) {
        var heightInMeters = height / 100; // convert cm to meters
        return weight / (heightInMeters * heightInMeters);
    }
</script>

</body>
</html>
