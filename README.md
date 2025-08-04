<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Timed Blackout</title>
    <style>
        /* Basic page styling */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f4f8;
            color: #1a202c;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 2rem;
            text-align: center;
        }

        /* Styles for the button to start the blackout */
        button {
            padding: 1rem 2rem;
            font-size: 1.25rem;
            font-weight: 700;
            cursor: pointer;
            border-radius: 0.5rem;
            border: none;
            background-color: #ef4444; /* A shade of red */
            color: white;
            transition: background-color 0.3s ease;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }
        
        button:hover {
            background-color: #dc2626;
        }

        /* Styles for the blackout overlay */
        .blackout-overlay {
            position: fixed; /* Ensures it covers the whole screen */
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: black; /* Solid black color */
            display: none; /* Hidden by default */
            justify-content: center;
            align-items: center;
            z-index: 9999; /* Puts it on top of all other content */
            color: white;
            font-size: 2.5rem;
            font-family: 'Inter', sans-serif;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }
    </style>
</head>
<body>
    <div class="content">
        <h1>Blackout Screen Timer</h1>
        <p>Click the button to start the 5-minute blackout with a surprise message.</p>
        <button onclick="startBlackout()">Start The Surprise</button>
    </div>

    <!-- This is the blackout overlay element, which is hidden until the button is clicked. -->
    <div id="blackout-overlay" class="blackout-overlay">
        The surprise from Nikhil
    </div>

    <script>
        // Get a reference to the blackout overlay element from the HTML
        const blackout = document.getElementById('blackout-overlay');

        // Function to start the blackout and the timer
        function startBlackout() {
            // Show the blackout screen
            blackout.style.display = 'flex';

            // Set a timer to hide the screen after 5 minutes (300,000 milliseconds)
            const durationInMilliseconds = 5 * 60 * 1000;
            setTimeout(() => {
                hideBlackout();
            }, durationInMilliseconds);
        }

        // Function to hide the blackout screen
        function hideBlackout() {
            blackout.style.display = 'none';
        }
    </script>
</body>
</html>
