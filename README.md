<!DOCTYPE html>
<html>
<head>
    <title>Survey Kepuasan Gaji - JNE</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 20px;
            background-color: #f5f5f5;
        }
        .jne-logo {
            width: 150px;
            margin-bottom: 20px;
        }
        .survey-container {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            width: 300px;
            margin: 0 auto;
            position: relative;
            min-height: 200px;
        }
        h1 {
            font-size: 18px;
            margin-bottom: 20px;
            color: #333;
        }
        .btn {
            padding: 10px 20px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
        }
        #yesBtn {
            background-color: #4CAF50;
            color: white;
        }
        #noBtn {
            background-color: #f44336;
            color: white;
            position: absolute;
        }
        .message {
            margin: 40px auto;
            padding: 30px;
            background-color: #ff0000;
            color: white;
            border-radius: 10px;
            display: none;
            font-weight: bold;
            font-size: 24px;
            width: 80%;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            animation: pulse 0.5s;
        }
        @keyframes pulse {
            0% { transform: scale(0.9); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        .hidden {
            display: none;
        }
        .laugh-gif {
            width: 180px;
            margin: 20px auto;
            display: none;
        }
        .footer {
            margin-top: 30px;
            padding: 20px;
            font-size: 12px;
            color: #666;
        }
    </style>
</head>
<body>
    <!-- Logo JNE di Awal -->
    <img src="https://www.jne.co.id/images/logo-jne.png" alt="Logo JNE" class="jne-logo">
    
    <div class="survey-container">
        <h1 id="question">APAKAH ANDA PUAS DENGAN GAJI ANDA SAAT INI?</h1>
        <button id="yesBtn" class="btn">YA</button>
        <button id="noBtn" class="btn">TIDAK</button>
        <div id="message" class="message">BAGUS, SEKARANG KEMBALI BEKERJA! 💼</div>
        <img id="laughGif" class="laugh-gif" src="https://media.giphy.com/media/p0RDMJGgMXF96/giphy.gif?cid=ecf05e47jse902dv719kvr05xat09d710syw2k7e3gnr1zqu&ep=v1_gifs_related&rid=giphy.gif&ct=g" alt="Tertawa ngakak">
    </div>

    <!-- Logo JNE di Akhir -->
    <div class="footer">
        <img src="https://www.jne.co.id/images/logo-jne.png" alt="Logo JNE" class="jne-logo" style="width: 120px;">
        <p>PT. Jalur Nugraha Ekakurir</p>
        <p>© 2024 Survey Kepuasan Karyawan</p>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const message = document.getElementById('message');
        const question = document.getElementById('question');
        const laughGif = document.getElementById('laughGif');
        
        // Make the "TIDAK" button run away
        noBtn.addEventListener('mouseover', function() {
            const container = this.parentElement;
            const containerRect = container.getBoundingClientRect();
            const btnRect = this.getBoundingClientRect();
            
            const maxX = containerRect.width - btnRect.width - 20;
            const maxY = containerRect.height - btnRect.height - 20;
            
            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);
            
            this.style.left = randomX + 'px';
            this.style.top = randomY + 'px';
        });
        
        // When "YA" is clicked
        yesBtn.addEventListener('click', function() {
            // Show message and GIF
            message.style.display = 'block';
            laughGif.style.display = 'block';
            
            // Hide question and buttons
            question.classList.add('hidden');
            yesBtn.classList.add('hidden');
            noBtn.classList.add('hidden');
        });
    </script>
</body>
</html>
