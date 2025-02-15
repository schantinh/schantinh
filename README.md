<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine Flower</title>
    <style>
        body {
            text-align: center;
            background-color: #f0e4d7;
            font-family: 'Arial', sans-serif;
        }
        #flower {
            width: 100px;
            height: 100px;
            background-color: #ff69b4;
            border-radius: 50%;
            margin: 50px auto;
            display: none;
        }
        #bloom {
            display: block;
            margin: 20px auto;
            padding: 10px 20px;
            background-color: #ff69b4;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Will you be my valentine?</h1>
    <button id="bloom">Yes, be my valentine</button>
    <div id="flower"></div>
    <p id="coffee"></p>

    <script>
        document.getElementById('bloom').addEventListener('click', function() {
            const flower = document.getElementById('flower');
            const coffee = document.getElementById('coffee');
            
            // Flower blooms
            flower.style.display = 'block';
            flower.style.transition = 'width 2s, height 2s';
            flower.style.width = '200px';
            flower.style.height = '200px';

            // Display coffee message
            coffee.textContent = 'Let’s have coffee! ☕️';
            coffee.style.color = '#8b4513';
            coffee.style.fontSize = '24px';
            coffee.style.marginTop = '20px';
        });
    </script>
</body>
</html>
