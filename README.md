<!DOCTYPE html>
<html lang="kk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Тойға шақыру | Ұкібай & Анаркүл</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    <!-- FontAwesome icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --gold: #D4AF37;
            --gold-light: #F3E5AB;
            --cream: #FFFDD0;
            --bg-cream: #FAF7F2;
            --dark: #2A2A2A;
            --white: #FFFFFF;
            --shadow: 0 10px 30px rgba(212, 175, 55, 0.15);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--bg-cream);
            color: var(--dark);
            overflow-x: hidden;
            position: relative;
        }

        /* Түскен гүл жапырақтарының анимация контейнері */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 10;
        }

        /* Ұлттық ою-өрнек фондағы декор */
        .ornament-bg {
            position: absolute;
            width: 300px;
            height: 300px;
            opacity: 0.05;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><path fill="%23D4AF37" d="M50 0 C60 25 75 40 100 50 C75 60 60 75 50 100 C40 75 25 60 0 50 C25 40 40 25 50 0 Z"/></svg>');
            background-size: contain;
            background-repeat: no-repeat;
            pointer-events: none;
        }

        .ornament-top-left { top: -50px; left: -50px; }
        .ornament-bottom-right { bottom: -50px; right: -50px; transform: rotate(180deg); }

        .container {
            max-width: 600px;
            margin: 0 auto;
            min-height: 100vh;
            background: var(--white);
            box-shadow: 0 0 50px rgba(0,0,0,0.05);
            position: relative;
            overflow: hidden;
        }

        /* Header / Main Hero section */
        .hero {
            padding: 80px 20px 50px;
            text-align: center;
            position: relative;
            background: linear-gradient(180deg, #FFFFFF 0%, var(--bg-cream) 100%);
            border-bottom: 1px solid rgba(212, 175, 55, 0.2);
        }

        .gold-border-frame {
            border: 2px solid var(--gold);
            padding: 40px 20px;
            border-radius: 150px 150px 0 0;
            position: relative;
            background: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(5px);
        }

        .gold-border-frame::before {
            content: "🌸";
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--white);
            padding: 0 10px;
            font-size: 20px;
        }

        .subtitle-top {
            font-size: 14px;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: var(--gold);
            margin-bottom: 20px;
        }

        .names {
            font-family: 'Cormorant Garamond', serif;
            font-size: 42px;
            font-weight: 700;
            color: var(--dark);
            line-height: 1.2;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #B8860B, #D4AF37, #AA771C);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .invitation-text {
            font-family: 'Cormorant Garamond', serif;
            font-size: 20px;
            font-style: italic;
            color: #555;
            line-height: 1.6;
            margin-top: 15px;
        }

        /* Details Section */
        .details-section {
            padding: 50px 25px;
            text-align: center;
        }

        .hosts {
            font-family: 'Cormorant Garamond', serif;
            font-size: 24px;
            color: var(--dark);
            margin-bottom: 35px;
            font-weight: 600;
        }

        .hosts span {
            color: var(--gold);
            display: block;
            font-size: 16px;
            font-family: 'Montserrat', sans-serif;
            font-weight: 400;
            margin-bottom: 5px;
            letter-spacing: 1px;
        }

        .info-card {
            background: var(--bg-cream);
            border-radius: 20px;
            padding: 25px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            text-align: left;
            border: 1px solid rgba(212, 175, 55, 0.3);
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
        }

        .info-card:hover {
            transform: translateY(-3px);
        }

        .info-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--gold), var(--gold-light));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 20px;
            margin-right: 20px;
            flex-shrink: 0;
        }

        .info-content h4 {
            font-size: 12px;
            text-transform: uppercase;
            color: #888;
            letter-spacing: 1px;
            margin-bottom: 3px;
        }

        .info-content p {
            font-size: 16px;
            font-weight: 600;
            color: var(--dark);
        }

        /* Countdown Timer */
        .timer-section {
            padding: 30px 20px;
            background: linear-gradient(135deg, #2A2A2A 0%, #1A1A1A 100%);
            color: var(--white);
            text-align: center;
            border-radius: 30px;
            margin: 20px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
        }

        .timer-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 22px;
            color: var(--gold-light);
            margin-bottom: 20px;
            letter-spacing: 1px;
        }

        .countdown {
            display: flex;
            justify-content: space-around;
        }

        .time-box {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .time-box .number {
            font-size: 28px;
            font-weight: 600;
            color: var(--gold);
        }

        .time-box .label {
            font-size: 11px;
            text-transform: uppercase;
            color: #AAA;
            margin-top: 5px;
        }

        /* RSVP Form Section */
        .rsvp-section {
            padding: 50px 25px;
            background: var(--white);
            text-align: center;
        }

        .section-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 32px;
            color: var(--gold);
            margin-bottom: 25px;
        }

        .rsvp-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .input-group input {
            width: 100%;
            padding: 16px;
            border: 1px solid #DDD;
            border-radius: 12px;
            font-family: 'Montserrat', sans-serif;
            font-size: 15px;
            outline: none;
            transition: border-color 0.3s;
            background: var(--bg-cream);
        }

        .input-group input:focus {
            border-color: var(--gold);
        }

        .radio-options {
            display: flex;
            gap: 15px;
        }

        .radio-btn {
            flex: 1;
            position: relative;
        }

        .radio-btn input {
            position: absolute;
            opacity: 0;
            cursor: pointer;
        }

        .radio-label {
            display: block;
            padding: 15px;
            border: 1px solid #DDD;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
            background: var(--bg-cream);
        }

        .radio-btn input:checked + .radio-label {
            border-color: var(--gold);
            background: var(--gold-light);
            color: var(--dark);
            font-weight: 600;
        }

        .submit-btn {
            background: linear-gradient(135deg, #D4AF37 0%, #AA771C 100%);
            color: var(--white);
            border: none;
            padding: 16px;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(212, 175, 55, 0.4);
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .submit-btn:active {
            transform: scale(0.98);
        }

        /* Success Message */
        .success-message {
            display: none;
            padding: 20px;
            background: #E8F5E9;
            color: #2E7D32;
            border-radius: 12px;
            font-size: 18px;
            font-family: 'Cormorant Garamond', serif;
            font-weight: 600;
            border: 1px solid #A5D6A7;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(100px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Falling Leaves Canvas */
        #leaf-canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 99;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 20px;
            font-size: 12px;
            color: #999;
            background: var(--bg-cream);
        }
    </style>
</head>
<body>

    <div class="container">
        <canvas id="leaf-canvas"></canvas>

        <div class="ornament-bg ornament-top-left"></div>
        <div class="ornament-bg ornament-bottom-right"></div>

        <!-- MAIN HERO -->
        <header class="hero">
            <div class="gold-border-frame">
                <div class="subtitle-top">Үйлену тойға шақыру</div>
                <h1 class="names">Ұкібай<br>&<br>Анаркүл</h1>
                <p class="invitation-text">«Сіздерді қуанышымыздың қадірлі қонағы болуға шақырамыз»</p>
            </div>
        </header>

        <!-- DETAILS SECTION -->
        <section class="details-section">
            <div class="hosts">
                <span>Той иелері:</span>
                Есенгелді & Жадыра
            </div>

            <div class="info-card">
                <div class="info-icon">
                    <i class="fa-regular fa-calendar-check"></i>
                </div>
                <div class="info-content">
                    <h4>Күні</h4>
                    <p>7 қазан</p>
                </div>
            </div>

            <div class="info-card">
                <div class="info-icon">
                    <i class="fa-regular fa-clock"></i>
                </div>
                <div class="info-content">
                    <h4>Уақыты</h4>
                    <p>19:00</p>
                </div>
            </div>

            <div class="info-card">
                <div class="info-icon">
                    <i class="fa-solid fa-utensils"></i>
                </div>
                <div class="info-content">
                    <h4>Мейрамхана</h4>
                    <p>[Мейрамхана атауы]</p>
                </div>
            </div>

            <div class="info-card">
                <div class="info-icon">
                    <i class="fa-solid fa-location-dot"></i>
                </div>
                <div class="info-content">
                    <h4>Мекенжайы</h4>
                    <p>[Мекенжай]</p>
                </div>
            </div>
        </section>

        <!-- COUNTDOWN TIMER -->
        <div class="timer-section">
            <div class="timer-title">Тойдың басталуына қалды:</div>
            <div class="countdown">
                <div class="time-box">
                    <span class="number" id="days">00</span>
                    <span class="label">Күн</span>
                </div>
                <div class="time-box">
                    <span class="number" id="hours">00</span>
                    <span class="label">Сағат</span>
                </div>
                <div class="time-box">
                    <span class="number" id="minutes">00</span>
                    <span class="label">Минут</span>
                </div>
                <div class="time-box">
                    <span class="number" id="seconds">00</span>
                    <span class="label">Секунд</span>
                </div>
            </div>
        </div>

        <!-- RSVP FORM SECTION -->
        <section class="rsvp-section">
            <h2 class="section-title">RSVP / Жауап беру</h2>
            
            <form id="rsvpForm" class="rsvp-form" onsubmit="handleRSVP(event)">
                <div class="input-group">
                    <input type="text" id="guestName" placeholder="Аты-жөніңізді енгізіңіз" required>
                </div>

                <div class="radio-options">
                    <div class="radio-btn">
                        <input type="radio" id="attending" name="status" value="Келемін" checked>
                        <label for="attending" class="radio-label">✅ Келемін</label>
                    </div>
                    <div class="radio-btn">
                        <input type="radio" id="notAttending" name="status" value="Келе алмаймын">
                        <label for="notAttending" class="radio-label">❌ Келе алмаймын</label>
                    </div>
                </div>

                <button type="submit" class="submit-btn">Жауапты жіберу</button>
            </form>

            <div id="successMessage" class="success-message">
                ✨ Жауабыңыз үшін рақмет!
            </div>
        </section>

        <footer>
            <p>Шақыру аккаунты • Ұкібай & Анаркүл</p>
        </footer>
    </div>

    <!-- JS: Timer & Falling Petals Script -->
    <script>
        // --- 1. COUNTDOWN TIMER ---
        // Тои күнiн көрсету (7 Қазан)
        const targetDate = new Date();
        targetDate.setMonth(9); // Қазан = 9 (0-ден басталады)
        targetDate.setDate(7);
        targetDate.setHours(19, 0, 0, 0);

        function updateCountdown() {
            const now = new Date();
            const difference = targetDate - now;

            if (difference > 0) {
                const days = Math.floor(difference / (1000 * 60 * 60 * 24));
                const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((difference % (1000 * 60)) / 1000);

                document.getElementById('days').innerText = days < 10 ? '0' + days : days;
                document.getElementById('hours').innerText = hours < 10 ? '0' + hours : hours;
                document.getElementById('minutes').innerText = minutes < 10 ? '0' + minutes : minutes;
                document.getElementById('seconds').innerText = seconds < 10 ? '0' + seconds : seconds;
            }
        }
        setInterval(updateCountdown, 1000);
        updateCountdown();

        // --- 2. RSVP FORM HANDLER ---
        function handleRSVP(event) {
            event.preventDefault();
            const form = document.getElementById('rsvpForm');
            const successMsg = document.getElementById('successMessage');
            
            form.style.display = 'none';
            successMsg.style.display = 'block';
        }

        // --- 3. PETALS / FLOWER ANIMATION (CANVAS) ---
        const canvas = document.getElementById('leaf-canvas');
        const ctx = canvas.getContext('2d');

        function resizeCanvas() {
            canvas.width = canvas.parentElement.clientWidth;
            canvas.height = canvas.parentElement.clientHeight;
        }
        resizeCanvas();
        window.addEventListener('resize', resizeCanvas);

        const petals = [];
        const petalCount = 15;

        class Petal {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height - canvas.height;
                this.size = Math.random() * 8 + 8;
                this.speedY = Math.random() * 1 + 0.5;
                this.speedX = Math.random() * 0.5 - 0.25;
                this.angle = Math.random() * 360;
                this.spin = Math.random() * 0.02 - 0.01;
            }

            update() {
                this.y += this.speedY;
                this.x += this.speedX;
                this.angle += this.spin;

                if (this.y > canvas.height) {
                    this.y = -10;
                    this.x = Math.random() * canvas.width;
                }
            }

            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.angle);
                ctx.fillStyle = 'rgba(212, 175, 55, 0.4)'; // Алтын-крем реңкті жапырақша
                ctx.beginPath();
                ctx.ellipse(0, 0, this.size, this.size / 2, 0, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        for (let i = 0; i < petalCount; i++) {
            petals.push(new Petal());
        }

        function animatePetals() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            petals.forEach(petal => {
                petal.update();
                petal.draw();
            });
            requestAnimationFrame(animatePetals);
        }
        animatePetals();
    </script>
</body>
</html>
