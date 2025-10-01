```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Глаз Бога - OSINT платформа</title>
    <style>
        :root {
            --primary-color: #1a1a2e;
            --secondary-color: #16213e;
            --accent-color: #0f3460;
            --highlight-color: #e94560;
            --text-color: #f1f1f1;
            --light-gray: #8f8f8f;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--primary-color);
            color: var(--text-color);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background-color: var(--secondary-color);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            width: 40px;
            height: 40px;
            background: var(--highlight-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 20px;
        }
        
        .logo-text {
            font-size: 24px;
            font-weight: 700;
        }
        
        .logo-text span {
            color: var(--highlight-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }
        
        nav a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav a:hover {
            color: var(--highlight-color);
        }
        
        /* Hero Section */
        .hero {
            padding: 100px 0;
            background: linear-gradient(135deg, var(--secondary-color) 0%, var(--primary-color) 100%);
            text-align: center;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 20px;
            max-width: 800px;
            margin: 0 auto 40px;
            color: var(--light-gray);
        }
        
        .cta-button {
            display: inline-block;
            background-color: var(--highlight-color);
            color: white;
            padding: 15px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            font-size: 18px;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(233, 69, 96, 0.4);
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(233, 69, 96, 0.6);
        }
        
        /* Features Section */
        .features {
            padding: 100px 0;
            background-color: var(--primary-color);
        }
        
        .section-title {
            text-align: center;
            font-size: 36px;
            margin-bottom: 60px;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--highlight-color);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background-color: var(--secondary-color);
            border-radius: 10px;
            padding: 30px;
            transition: transform 0.3s;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
        }
        
        .feature-icon {
            width: 60px;
            height: 60px;
            background-color: var(--accent-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            font-size: 24px;
        }
        
        .feature-card h3 {
            font-size: 22px;
            margin-bottom: 15px;
        }
        
        .feature-card p {
            color: var(--light-gray);
        }
        
        /* Bots Section */
        .bots {
            padding: 100px 0;
            background-color: var(--secondary-color);
        }
        
        .bots-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 40px;
        }
        
        .bot-card {
            background-color: var(--primary-color);
            border-radius: 15px;
            padding: 40px;
            width: 100%;
            max-width: 500px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }
        
        .bot-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--accent-color), var(--highlight-color));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 30px;
        }
        
        .bot-card h3 {
            font-size: 24px;
            margin-bottom: 15px;
        }
        
        .bot-card p {
            color: var(--light-gray);
            margin-bottom: 25px;
        }
        
        .bot-username {
            display: inline-block;
            background-color: var(--accent-color);
            padding: 10px 20px;
            border-radius: 20px;
            font-family: monospace;
            font-size: 18px;
            margin-bottom: 25px;
        }
        
        .bot-button {
            display: inline-block;
            background-color: var(--highlight-color);
            color: white;
            padding: 12px 25px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .bot-button:hover {
            background-color: #d43c55;
            transform: translateY(-3px);
        }
        
        /* How It Works */
        .how-it-works {
            padding: 100px 0;
            background-color: var(--primary-color);
        }
        
        .steps {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            margin-top: 50px;
        }
        
        .step {
            flex: 1;
            min-width: 250px;
            text-align: center;
            padding: 30px 20px;
        }
        
        .step-number {
            width: 50px;
            height: 50px;
            background-color: var(--highlight-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-weight: bold;
            font-size: 20px;
        }
        
        .step h3 {
            margin-bottom: 15px;
        }
        
        .step p {
            color: var(--light-gray);
        }
        
        /* CTA Section */
        .cta-section {
            padding: 100px 0;
            background: linear-gradient(135deg, var(--accent-color) 0%, var(--secondary-color) 100%);
            text-align: center;
        }
        
        .cta-section h2 {
            font-size: 36px;
            margin-bottom: 20px;
        }
        
        .cta-section p {
            font-size: 18px;
            max-width: 700px;
            margin: 0 auto 40px;
            color: rgba(255, 255, 255, 0.8);
        }
        
        /* Footer */
        footer {
            background-color: var(--secondary-color);
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column {
            flex: 1;
            min-width: 200px;
        }
        
        .footer-column h3 {
            margin-bottom: 20px;
            font-size: 20px;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column a {
            color: var(--light-gray);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column a:hover {
            color: var(--highlight-color);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--light-gray);
            font-size: 14px;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 20px;
            }
            
            nav ul {
                gap: 15px;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .section-title {
                font-size: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">GB</div>
                    <div class="logo-text">Глаз <span>Бога</span></div>
                </div>
                <nav>
                    <ul>
                        <li><a href="#features">Возможности</a></li>
                        <li><a href="#bots">Боты</a></li>
                        <li><a href="#how-it-works">Как работает</a></li>
                        <li><a href="#start">Начать</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Мощный OSINT-инструмент в вашем Telegram</h1>
            <p>Глаз Бога — российская платформа для анализа больших данных из открытых источников. Получите сведения о людях и компаниях с помощью интуитивного интерфейса Telegram-бота.</p>
            <a href="#bots" class="cta-button">Начать использовать</a>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Возможности платформы</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">🔍</div>
                    <h3>Поиск по открытым источникам</h3>
                    <p>Анализ данных из социальных сетей, мессенджеров, поисковых систем и других открытых источников.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔗</div>
                    <h3>Выявление взаимосвязей</h3>
                    <p>Обнаружение совпадений между объектами и установление предполагаемых взаимосвязей.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <h3>Структурирование данных</h3>
                    <p>Автоматическое структурирование полученных данных в удобном для анализа виде.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">👤</div>
                    <h3>Поиск по физическим лицам</h3>
                    <p>Получение информации о людях по различным параметрам и идентификаторам.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🏢</div>
                    <h3>Анализ организаций</h3>
                    <p>Проверка компаний и контрагентов перед совершением сделок.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🚗</div>
                    <h3>Поиск по транспорту и контактам</h3>
                    <p>Получение данных о транспортных средствах, номерах телефонов и электронных почтах.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Bots Section -->
    <section class="bots" id="bots">
        <div class="container">
            <h2 class="section-title">Наши Telegram-боты</h2>
            <div class="bots-container">
                <div class="bot-card">
                    <div class="bot-icon">GB</div>
                    <h3>GlazBoga_Off_Bot</h3>
                    <p>Основной бот платформы "Глаз Бога" для комплексного анализа данных из открытых источников.</p>
                    <div class="bot-username">@GlazBoga_Off_Bot</div>
                    <a href="https://t.me/GlazBoga_Off_Bot" class="bot-button" target="_blank">Открыть в Telegram</a>
                </div>
                <div class="bot-card">
                    <div class="bot-icon">OI</div>
                    <h3>oiosintbot</h3>
                    <p>Специализированный бот для OSINT-расследований и анализа открытой информации.</p>
                    <div class="bot-username">@oiosintbot</div>
                    <a href="https://t.me/oiosintbot" class="bot-button" target="_blank">Открыть в Telegram</a>
                </div>
            </div>
        </div>
    </section>

    <!-- How It Works -->
    <section class="how-it-works" id="how-it-works">
        <div class="container">
            <h2 class="section-title">Как это работает</h2>
            <div class="steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Выберите бота</h3>
                    <p>Откройте одного из наших Telegram-ботов</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Введите запрос</h3>
                    <p>Задайте интересующий вас объект поиска</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Получите результат</h3>
                    <p>Система проанализирует данные и предоставит структурированный отчет</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Проанализируйте</h3>
                    <p>Используйте полученные данные для своих целей</p>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section" id="start">
        <div class="container">
            <h2>Начните использовать Глаз Бога прямо сейчас</h2>
            <p>Присоединяйтесь к тысячам пользователей, которые уже используют нашу платформу для анализа данных и поиска информации.</p>
            <a href="#bots" class="cta-button">Выбрать бота</a>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Глаз Бога</h3>
                    <p>Российская платформа для анализа больших данных из открытых источников.</p>
                </div>
                <div class="footer-column">
                    <h3>Наши боты</h3>
                    <ul>
                        <li><a href="https://t.me/GlazBoga_Off_Bot" target="_blank">@GlazBoga_Off_Bot</a></li>
                        <li><a href="https://t.me/oiosintbot" target="_blank">@oiosintbot</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Информация</h3>
                    <ul>
                        <li><a href="#features">Возможности</a></li>
                        <li><a href="#how-it-works">Как работает</a></li>
                        <li><a href="#bots">Боты</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 Глаз Бога. Все права защищены.</p>
            </div>
        </div>
    </footer>

    <script>
        // Плавная прокрутка для навигационных ссылок
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
