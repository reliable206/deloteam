<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reliable - DELO TEAM</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        /* --- NOWA ANIMACJA TŁA: BARDZO WOLNY PŁYNĄCY RUCH --- */
        @keyframes flow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* --- CUSTOMOWY PASEK PRZEWIJANIA --- */
        ::-webkit-scrollbar { width: 12px; }
        ::-webkit-scrollbar-track { background: #e0f7fa; }
        ::-webkit-scrollbar-thumb {
            background-color: #4fa3d1;
            border-radius: 10px;
            border: 3px solid #e0f7fa;
        }
        ::-webkit-scrollbar-thumb:hover { background-color: #002f4b; }
        html { scrollbar-width: thin; scrollbar-color: #4fa3d1 #e0f7fa; }

        /* --- STYL OGÓLNY --- */
        body {
            margin: 0;
            padding: 0;
            font-family: 'Montserrat', sans-serif;
            color: #002f4b;
            min-height: 100vh;
            overflow-x: hidden;
            display: flex;
            flex-direction: column;

            /* Uproszczone, animowane tło */
            background: linear-gradient(-45deg, #e0f7fa, #cce4f7, #aed6f1, #e0f7fa);
            
            background-size: 400% 400%; /* Duży rozmiar gradientu */
            background-attachment: fixed;
            animation: flow 20s ease infinite; /* Płynna, wolna animacja */
        }

        .main-wrapper {
            flex-grow: 1;
            max-width: 1000px;
            width: 90%;
            margin: 0 auto;
            padding: 40px 0;
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* --- NAGŁÓWEK "RELIABLE" --- */
        .hero-title {
            font-size: 8.5vw; 
            white-space: nowrap; 
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin: 30px 0 50px 0;
            line-height: 1;
            
            background: linear-gradient(to right, #002f4b 20%, #4fa3d1 50%, #002f4b 80%);
            background-size: 200% auto;
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            animation: shine 4s linear infinite;
        }

        @keyframes shine {
            to { background-position: 200% center; }
        }

        /* --- SEKCJA O GRUPIE --- */
        .intro-section {
            background: rgba(255, 255, 255, 0.5);
            padding: 30px;
            border-radius: 20px;
            margin-bottom: 50px;
            box-shadow: 0 4px 15px rgba(0, 47, 75, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.6);
            width: 100%;
            box-sizing: border-box;
        }

        .intro-section h2 {
            font-size: 2rem;
            margin-top: 0;
            margin-bottom: 15px;
            color: #002f4b;
        }

        .intro-section p {
            font-size: 1.1rem;
            line-height: 1.6;
            margin: 0 auto;
        }

        /* --- SIATKA CZŁONKÓW --- */
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 25px;
            padding-bottom: 50px;
            width: 100%;
        }

        .member-card {
            background: rgba(255, 255, 255, 0.8);
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(5px);
        }

        .member-card:hover {
            transform: translateY(-7px);
            box-shadow: 0 15px 30px rgba(0, 47, 75, 0.15);
        }

        .member-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 6px;
            background: linear-gradient(90deg, #4fa3d1, #002f4b);
        }

        .member-name {
            font-size: 1.6rem;
            font-weight: 800;
            margin: 15px 0 5px 0;
            color: #002f4b;
        }

        .member-details {
            font-weight: 500;
            color: #546e7a;
        }

        .member-date {
            font-size: 0.95rem;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 8px;
            margin-bottom: 5px;
        }
        
        .member-city {
            font-size: 0.85rem;
            color: #607d8b;
            margin-bottom: 10px;
        }

        .icon { font-size: 1.2em; }

        /* --- STOPKA Z PRZYCISKAMI --- */
        footer {
            margin-top: auto;
            padding: 40px 20px 60px 20px;
            text-align: center;
            background: linear-gradient(135deg, #cce4f7 0%, #aed6f1 100%);
            border-top: 1px solid rgba(255, 255, 255, 0.5);
            width: 100%;
            box-sizing: border-box;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 20px;
        }
        
        @media (min-width: 768px) {
            .footer-content {
                flex-direction: row;
                justify-content: space-around;
                max-width: 800px;
                margin: 0 auto;
            }
        }

        .footer-logo img {
            max-width: 250px;
            width: 100%;
            height: auto;
            display: block;
            margin-bottom: 20px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .social-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
        }

        .footer-heading {
            font-size: 1.2rem;
            font-weight: 700;
            color: #002f4b;
            margin: 0; 
        }

        .social-buttons {
            display: flex;
            gap: 15px;
            flex-direction: column;
        }

        @media (min-width: 768px) {
            .social-buttons {
                flex-direction: row;
            }
        }
        
        .social-btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 10px 15px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: background-color 0.3s, transform 0.1s;
            color: white;
            box-shadow: 0 4px 6px rgba(0, 47, 75, 0.2);
        }

        .social-btn.marcel {
            background-color: #4fa3d1;
        }
        .social-btn.marcel:hover {
            background-color: #002f4b;
            transform: translateY(-2px);
        }

        .social-btn.oliwier {
            background-color: #66bb6a;
        }
        .social-btn.oliwier:hover {
            background-color: #388e3c;
            transform: translateY(-2px);
        }

        .social-btn i {
            font-size: 1.2em;
        }

    </style>
</head>
<body>

    <div class="main-wrapper">
        
        <h1 class="hero-title">RELIABLE</h1>

        <div class="intro-section">
            <h2>DELO TEAM</h2>
            <p>
                Grupa powstała w <strong>kwietniu 2022 roku</strong> i nieprzerwanie istnieje do dzisiaj.<br>
                Tworzymy zgraną ekipę, którą łączą wspólne pasje i cele.
            </p>
        </div>

        <div class="team-grid">
            
            <div class="member-card">
                <div class="member-name">Diamo</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 22 września 2006</div>
                    <div class="member-city">Rawicz</div>
                </div>
            </div>

            <div class="member-card">
                <div class="member-name">Daniel</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 28 listopada 2006</div>
                    <div class="member-city">Radocza (obecnie Gdańsk)</div>
                </div>
            </div>

            <div class="member-card">
                <div class="member-name">Najam</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 16 kwietnia 2007</div>
                    <div class="member-city">Białystok</div>
                </div>
            </div>

            <div class="member-card">
                <div class="member-name">Solka</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 17 czerwca 2008</div>
                    <div class="member-city">Promnice</div>
                </div>
            </div>

            <div class="member-card">
                <div class="member-name">Dangap</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 14 lipca 2009</div>
                    <div class="member-city">Tomaszów Mazowiecki</div>
                </div>
            </div>

            <div class="member-card">
                <div class="member-name">Brunet</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 14 września 2009</div>
                    <div class="member-city">Świebodzin</div>
                </div>
            </div>

            <div class="member-card">
                <div class="member-name">Lukiś</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 3 listopada 2009</div>
                    <div class="member-city">Bańkowszczyzna</div>
                </div>
            </div>

            <div class="member-card">
                <div class="member-name">Marcel</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 8 stycznia 2010</div>
                    <div class="member-city">Nowy Dwór Mazowiecki</div>
                </div>
            </div>

            <div class="member-card">
                <div class="member-name">Oliwier</div>
                <div class="member-details">
                    <div class="member-date"><span class="icon">🎂</span> 2 maja 2010</div>
                    <div class="member-city">Sopot</div>
                </div>
            </div>

        </div>
    </div>

    <footer>
        <div class="footer-content">
            
            <div class="footer-logo">
                <img src="deloo.png" alt="DELO TEAM Logo"> </div>

            <div class="social-section">
                <p class="footer-heading">Instagramy twórców strony – polecamy oblukać! 👇</p>
                <div class="social-buttons">
                    <a href="https://www.instagram.com/maarcell_mm/" target="_blank" class="social-btn marcel">
                        <i class="fab fa-instagram"></i>
                        Instagram Marcela
                    </a>
                    
                    <a href="https://www.instagram.com/vx.oliwier_/" target="_blank" class="social-btn oliwier">
                        <i class="fab fa-instagram"></i>
                        Instagram Oliwiera
                    </a>
                </div>
            </div>
            
        </div>
    </footer>

</body>
</html>
