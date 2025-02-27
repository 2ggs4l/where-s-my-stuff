<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Where’s My Stuff? - AI Finder</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 600px;
            margin: auto;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        input {
            padding: 10px;
            font-size: 16px;
            width: 80%;
            margin: 10px 0;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            background-color: #007bff;
            color: white;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        .response {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            color: #333;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Where’s My Stuff?</h1>
        <p><strong>Problem:</strong> People waste time searching for lost items like keys, wallets, and remotes.</p>
        <p><strong>Solution:</strong> Our AI-powered assistant predicts where your lost items are based on past habits.</p>
        <input type="text" id="itemInput" placeholder="Enter the item you lost...">
        <button id="findButton">Ask AI: Where’s My Stuff?</button>
        <p class="response" id="aiResponse"></p>
    </div>
    
    <script>
        (function() {
            document.addEventListener("DOMContentLoaded", function() {
                const findButton = document.getElementById("findButton");
                findButton.addEventListener("click", findItem);
            });

            function findItem() {
                const item = document.getElementById("itemInput").value.trim();
                if (!item) {
                    document.getElementById("aiResponse").innerText = "Please enter an item to search for.";
                    return;
                }
                
                const locations = [
                    `Your ${item} was last seen on the kitchen counter.`,
                    `Your ${item} might be near the couch where you sat earlier.`,
                    `Check your bedroom desk for your ${item}.`,
                    `Your ${item} was last used in the living room.`,
                    `Look in your jacket pocket for your ${item}.`
                ];
                
                const randomLocation = locations[Math.floor(Math.random() * locations.length)];
                document.getElementById("aiResponse").innerText = randomLocation;
            }
        })();
    </script>
</body>
</html>
