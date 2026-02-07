<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Urgent: Security Alert</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #fff0f0;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            overflow: hidden;
            touch-action: manipulation;
        }

        .card {
            text-align: center;
            background: white;
            padding: 40px;
            border-radius: 24px;
            box-shadow: 0 15px 35px rgba(255, 100, 100, 0.15);
            width: 85%;
            max-width: 400px;
            position: relative;
        }

        h1 {
            color: #d63384;
            font-size: 1.8rem;
            margin-bottom: 40px;
            line-height: 1.3;
        }

        .btn-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            min-height: 50px;
        }

        .btn {
            font-size: 1.1rem;
            font-weight: bold;
            padding: 12px 30px;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            transition: transform 0.1s ease;
            display: inline-block;
        }

        #yesBtn {
            background-color: #ff4d6d;
            color: white;
        }

        /* Fixed: No absolute position at start */
        #noBtn {
            background-color: #f0f0f0;
            color: #555;
            position: relative; 
            z-index: 999;
        }
    </style>
</head>
<body>

    <div class="card">
        <h1>Will you be my valentine drishya ❤️</h1>
        <div class="btn-container">
            <button class="btn" id="yesBtn" onclick="sayYes()">Yes</button>
            <button class="btn" id="noBtn" onmouseover="moveButton()" ontouchstart="moveButton()">No</button>
        </div>
    </div>

    <script>
        function moveButton() {
            const noBtn = document.getElementById('noBtn');
            
            // The first time she interacts, we switch it to absolute
            if (noBtn.style.position !== 'absolute') {
                noBtn.style.position = 'absolute';
            }

            // Calculate random coordinates 
            // We use 150/100 as buffers to keep it from going off-screen
            const x = Math.random() * (window.innerWidth - 150);
            const y = Math.random() * (window.innerHeight - 100);

            noBtn.style.left = x + 'px';
            noBtn.style.top = y + 'px';
        }

        function sayYes() {
            const thankYouPage = `
                <html>
                <head>
                    <meta name="viewport" content="width=device-width, initial-scale=1.0">
                    <title>Success!</title>
                </head>
                <body style="background-color: #ff4d6d; color: white; display: flex; flex-direction: column; justify-content: center; align-items: center; height: 100vh; margin: 0; font-family: sans-serif; text-align: center;">
                    <h1 style="font-size: 3rem;">thankyou baby! 💖</h1>
                    <p style="font-size: 1.5rem;">Best decision ever!</p>
                </body>
                </html>
            `;
            
            const win = window.open("", "_blank");
            win.document.write(thankYouPage);
            win.document.close();
        }
    </script>
</body>
</html>
