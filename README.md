<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prank Horror</title>
    <style>
        body {
            margin: 0;
            background: black;
            text-align: center;
            overflow: hidden;
        }
        video {
            width: 100%;
            height: 100vh;
            object-fit: cover;
            display: none; /* Sembunyikan sampai tombol ditekan */
        }
        #jumpscare {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            background: black;
            justify-content: center;
            align-items: center;
        }
        #jumpscare img {
            width: 100%;
            height: 100vh;
            object-fit: cover;
        }
        #startBtn {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 20px;
            font-size: 20px;
            background: red;
            color: white;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <!-- Tombol untuk memulai prank -->
    <button id="startBtn" onclick="startScare()">Mulai</button>

    <!-- Video Seram -->
    <video id="scaryVideo" loop>
        <source src="https://drive.google.com/uc?export=download&id=17xirr6WBU11N42S9TKSUhCP_i1Y1r8r1" type="video/mp4">
    </video>

    <!-- Musik Seram -->
    <audio id="scaryMusic" loop>
        <source src="https://drive.google.com/uc?export=download&id=17xIc4UgPwPbjyZAPOKhQ7mgHEUUzInxe" type="audio/mp3">
    </audio>

    <!-- Jumpscare -->
    <div id="jumpscare">
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/2a/The_Exorcist_1973.jpg" alt="Jumpscare">
        <audio id="screamSound">
            <source src="https://www.fesliyanstudios.com/play-mp3/4381" type="audio/mp3">
        </audio>
    </div>

    <script>
        function startScare() {
            // Sembunyikan tombol mulai
            document.getElementById("startBtn").style.display = "none";
            
            // Tampilkan video dan mulai memutar
            let video = document.getElementById("scaryVideo");
            video.style.display = "block";
            video.play();

            // Mulai musik seram
            document.getElementById("scaryMusic").play();

            // Jumpscare setelah 3 detik
            setTimeout(() => {
                document.getElementById("jumpscare").style.display = "flex";
                document.getElementById("screamSound").play();
            }, 3000);
        }
    </script>

</body>
</html>
