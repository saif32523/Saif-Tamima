<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Envelope Proposal</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            background-color: #f0e6f6;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }
        .envelope-wrapper {
            position: relative;
            width: 280px;
            height: 180px;
        }
        #envelope {
            position: relative;
            width: 280px;
            height: 180px;
            border-bottom-left-radius: 6px;
            border-bottom-right-radius: 6px;
            background-color: #d9534f;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }
        .front {
            position: absolute;
            width: 0;
            height: 0;
            z-index: 3;
        }
        .flap {
            border-left: 140px solid transparent;
            border-right: 140px solid transparent;
            border-bottom: 82px solid transparent;
            border-top: 98px solid #d9534f;
            transform-origin: top;
            pointer-events: none;
        }
        .pocket {
            border-left: 140px solid #f5a3a2;
            border-right: 140px solid #f5a3a2;
            border-bottom: 90px solid #ff6f61;
            border-top: 90px solid transparent;
            border-bottom-left-radius: 6px;
            border-bottom-right-radius: 6px;
        }
        .letter {
            position: relative;
            background-color: #fff;
            width: 90%;
            margin-left: auto;
            margin-right: auto;
            height: 90%;
            top: 5%;
            border-radius: 6px;
            box-shadow: 0 2px 26px rgba(0, 0, 0, 0.12);
            font-family: "Dancing Script", cursive;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }
        .words {
            text-align: center;
            font-size: 1.2rem;
            color: #d9534f;
        }
        .open .flap {
            transform: rotateX(180deg);
            transition: transform 0.4s ease, z-index 0.6s;
            z-index: 1;
        }
        .close .flap {
            transform: rotateX(0deg);
            transition: transform 0.4s 0.6s ease, z-index 1s;
            z-index: 5;
        }
        .close .letter {
            transform: translateY(0px);
            transition: transform 0.4s ease, z-index 1s;
            z-index: 1;
        }
        .open .letter {
            transform: translateY(-100px);
            transition: transform 0.4s 0.6s ease, z-index 0.6s;
            z-index: 2;
        }
        .reset {
            text-align: center;
            margin-top: 20px;
        }
        .reset button {
            font-weight: 800;
            background-color: transparent;
            border: solid 2px #d9534f;
            border-radius: 4px;
            color: #d9534f;
            font-size: 14px;
            text-transform: uppercase;
            padding: 10px;
            cursor: pointer;
            margin: 5px;
        }
        .reset button:hover {
            background-color: #d9534f;
            color: #fff;
        }
    </style>
</head>
<body>
    <div class="envelope-wrapper">
        <div id="envelope" class="close">
            <div class="front flap"></div>
            <div class="front pocket"></div>
            <div class="letter">
                <p class="words">You’re Invited!

Saif & Tamima joyfully invite you to celebrate their wedding!

📅 21st March | ⏰ 4:00 PM | 📍 Buffet Carnival, Dhanmondi</p>
            </div>
        </div>
    </div>
    <div class="reset">
        <button onclick="openEnvelope()">Open</button>
        <button onclick="closeEnvelope()">Close</button>
    </div>

    <script>
        function openEnvelope() {
            document.getElementById("envelope").classList.add("open");
            document.getElementById("envelope").classList.remove("close");
        }
        function closeEnvelope() {
            document.getElementById("envelope").classList.add("close");
            document.getElementById("envelope").classList.remove("open");
        }
    </script>
</body>
</html>
