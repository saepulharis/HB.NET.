<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>HB.NET Login</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            background: linear-gradient(to right, #141e30, #243b55);
            color: white;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }
        .container {
            background: rgba(0,0,0,0.5);
            padding: 30px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 0 20px rgba(0,0,0,0.6);
        }
        input {
            width: 80%;
            padding: 12px;
            margin: 15px 0;
            border: none;
            border-radius: 6px;
            font-size: 16px;
        }
        button {
            padding: 12px 25px;
            border: none;
            border-radius: 6px;
            background: #28a745;
            color: white;
            font-weight: bold;
            cursor: pointer;
        }
        .message, .footer {
            margin-top: 30px;
        }
        .footer {
            font-size: 0.8rem;
            color: #ccc;
        }
    </style>
</head>
<body>
    <div class="container" id="login-container">
        <h1>Wi-Fi HB.NET</h1>
        <p>HARIS BULAK NETWORK</p>
        <input type="text" id="username" placeholder="Masukkan nama Anda">
        <button onclick="prosesLogin()">Login</button>
    </div>

    <div class="container message" id="message-container" style="display:none;">
        <h2 id="welcome-msg"></h2>
        <p>SEMOGA INTERNET NYA LANCAR DAN SEMOGA KAMU BISA CHTAN SAMA PASANGANNYA KEKASIH DENGAN LANCAR TANPA GANGUAN</p>
        <p style="color: yellow;">INFORMASI: SAAT INTERNET JANGAN BUKA WEBSITE YANG ANEH-ANEH</p>
        <p><strong id="tanggal"></strong></p>
    </div>

    <div class="footer">
        Hak cipta © Saepul Haris27 tahun 2025
    </div>

    <script>
        function prosesLogin() {
            const nama = document.getElementById("username").value.trim();
            if(nama){
                document.getElementById("login-container").style.display = "none";
                document.getElementById("message-container").style.display = "block";
                document.getElementById("welcome-msg").innerText = `Selamat datang ${nama}, semoga harimu menyenangkan!`;

                setTimeout(() => {
                    window.location.href = "https://www.google.com";
                }, 5000); // Redirect ke Google setelah 5 detik
            }
        }

        function tampilTanggal() {
            const now = new Date();
            const formatter = new Intl.DateTimeFormat('id-ID', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' });
            document.getElementById("tanggal").innerText = formatter.format(now);
        }

        window.onload = tampilTanggal;
    </script>
</body>
</html>
