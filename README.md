# Dalat-countdown
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Đếm ngược đến 12/06/2026</title>
<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
        margin-top: 100px;
        background: #f5f5f5;
    }
    h1 {
        margin-bottom: 30px;
    }
    #countdown {
        font-size: 40px;
        font-weight: bold;
    }
</style>
</head>
<body>

<h1>Đếm ngược đến ngày 12/06/2026:</h1>
<p id="target-time"></p>
<div id="countdown"></div>

<script>
    // Đếm ngược đến 12/06/2026 00:00:00
    const TARGET = new Date("2026-06-12T00:00:00").getTime();

    document.getElementById("target-time").innerText =
        new Date(TARGET).toLocaleString("vi-VN");

    function updateCountdown() {
        const now = new Date().getTime();
        const distance = TARGET - now;

        if (distance < 0) {
            document.getElementById("countdown").innerHTML = "Hết thời gian!";
            return;
        }

        const days = Math.floor(distance / (1000 * 60 * 60 * 24));
        const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((distance % (1000 * 60)) / 1000);

        document.getElementById("countdown").innerHTML =
            `${days} ngày ${hours} giờ ${minutes} phút ${seconds} giây`;
    }

    setInterval(updateCountdown, 1000);
    updateCountdown();
</script>

</body>
</html>
