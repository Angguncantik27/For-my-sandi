<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Love Letter</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #ffe6e6;
            font-family: 'Comic Sans MS', sans-serif;
            text-align: center;
        }

        .heart, .content {
            position: relative;
            display: none;
            flex-direction: column;
            align-items: center;
        }

        .heart img {
            width: 100px;
            height: auto;
            animation-name: beat;
            animation-duration: 2s;
            animation-timing-function: ease-in-out;
            animation-iteration-count: infinite;
            cursor: pointer;
        }

        @keyframes beat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
        }

        .content img {
            max-width: 250px;
            height: auto;
            margin-bottom: 10px;
        }

        #contentText {
            color: red;
            font-size: 18px;
            font-weight: bold;
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .buttons {
            margin-top: 20px;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 20px;
            font-size: 16px;
            cursor: pointer;
            background-color: #ff6666;
            color: white;
            margin: 5px;
        }

        button:hover {
            background-color: #ff3333;
        }

        #message {
            margin-bottom: 20px;
            font-size: 20px;
            color: red;
            font-weight: bold;
            animation: pulse 1.5s infinite;
        }
    </style>
</head>
<body>
    <div id="message">Pencet love-nya ya sayang ❤️</div>
    <div class="heart" id="heart">
        <img src="https://i.ibb.co/k21Y4mt9/37139-BDC-39-B7-42-C8-ACA1-9134-C11-C9181.png" alt="Heart">
    </div>
    <div class="content" id="content">
        <img id="contentImage" src="" alt="Content">
        <p id="contentText"></p>
        <div class="buttons">
            <button id="nextButton">Next</button>
            <button id="yesButton" style="display: none;">Iya</button>
            <button id="noButton" style="display: none;">Tidak</button>
        </div>
    </div>

    <script>
        const heartElement = document.getElementById('heart');
        const contentElement = document.getElementById('content');
        const contentImage = document.getElementById('contentImage');
        const contentText = document.getElementById('contentText');
        const nextButton = document.getElementById('nextButton');
        const yesButton = document.getElementById('yesButton');
        const noButton = document.getElementById('noButton');
        const messageElement = document.getElementById('message');

        const messages = [
            { text: "Pagi pacarku sandi sayang😍", image: "https://i.ibb.co/qw1j6mt/IMG-2460.jpg" },
            { text: "Sayang, maafin anggun ya belum bisa jadi pacar yang baik😞", image: "https://i.ibb.co/jkCcvNBs/IMG-2265.jpg" },
            { text: "Makasih disetiap salahnya sayang masih mau tetap sabar dan berubah demi anggun😊", image: "https://i.ibb.co/v4snk95z/IMG-1743.jpg" },
            { text: "Anggun bakal berusaha juga berubah untuk hubungan kita🥰", image: "https://i.ibb.co/ksh3kqCS/IMG-1355.jpg" },
            { text: "Sayang jangan pernah tinggalin anggun ya, jangan pernah lelah sama kita😇", image: "https://i.ibb.co/PGqZzDYW/IMG-8780.jpg" },
            { text: "Love u sandi ku sayang❤️", image: "https://i.ibb.co/JjCpJNGf/IMG-7374.jpg" },
            { text: "sayang sedia gak sama anggun terus??", image: "https://i.ibb.co/WNbtwnyy/IMG-2319.jpg" }
        ];

        let currentIndex = 0;

        heartElement.style.display = "flex";

        heartElement.addEventListener('click', () => {
            heartElement.style.display = "none";
            messageElement.style.display = "none";
            contentElement.style.display = "flex";
            showMessage(currentIndex);
        });

        nextButton.addEventListener('click', () => {
            currentIndex++;
            if (currentIndex < messages.length - 1) {
                showMessage(currentIndex);
            } else if (currentIndex === messages.length - 1) {
                showMessage(currentIndex);
                nextButton.style.display = "none";
                yesButton.style.display = "inline-block";
                noButton.style.display = "inline-block";
            }
        });

        yesButton.addEventListener("click", () => {
            contentText.textContent = "Makasih cayanggg🥺";
            contentImage.src = "https://i.ibb.co/N2bcXXyG/IMG-3887.jpg";
            yesButton.style.display = "none";
            noButton.style.display = "none";
        });

        noButton.addEventListener("click", () => {
            // No action
        });

        function showMessage(index) {
            contentImage.src = messages[index].image;
            contentText.textContent = messages[index].text;
        }
    </script>
</body>
</html>
