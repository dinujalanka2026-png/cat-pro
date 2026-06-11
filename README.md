<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kids' Cat World | ළමා පූස් ලෝකය | பூனை உலகம்</title>
    <!-- Google Fonts: Fredoka for rounded kid-friendly typography -->
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-gradient: radial-gradient(circle at 10% 20%, rgba(255, 249, 230, 1) 0%, rgba(255, 230, 235, 1) 50%, rgba(230, 247, 255, 1) 100%);
            --primary-color: #ff6f91;
            --primary-hover: #ff477e;
            --secondary-color: #845ef7;
            --accent-color: #ffc048;
            --text-dark: #2c3e50;
            --text-light: #ffffff;
            --card-shadow: 0 15px 30px rgba(255, 111, 145, 0.12);
            --transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Fredoka', sans-serif;
            background: var(--bg-gradient);
            color: var(--text-dark);
            min-height: 100vh;
            overflow-x: hidden;
            padding-bottom: 50px;
        }

        /* Ambient animated background bubbles */
        .ambient-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.05;
            pointer-events: none;
        }

        .bubble {
            position: absolute;
            background: rgba(255, 111, 145, 0.15);
            border-radius: 50%;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translateY(100vh) scale(0.5); opacity: 0; }
            50% { opacity: 0.8; }
            100% { transform: translateY(-10vh) scale(1.2); opacity: 0; }
        }

        /* Header Style */
        header {
            text-align: center;
            padding: 40px 20px 20px 20px;
            position: relative;
        }

        .header-content {
            max-width: 1000px;
            margin: 0 auto;
        }

        /* Hero Image Container */
        .hero-img-container {
            width: 100%;
            max-width: 650px;
            margin: 0 auto 30px auto;
            border-radius: 30px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(132, 94, 247, 0.25);
            border: 8px solid white;
            transform: rotate(-1.5deg);
            transition: var(--transition);
        }

        .hero-img-container:hover {
            transform: rotate(1deg) scale(1.02);
        }

        .hero-img-container img {
            width: 100%;
            height: auto;
            display: block;
        }

        h1 {
            font-size: 3.2rem;
            color: var(--secondary-color);
            text-shadow: 3px 3px 0px white, 6px 6px 0px rgba(0,0,0,0.05);
            margin-bottom: 10px;
            animation: bounceIn 1s ease;
        }

        .subtitle {
            font-size: 1.3rem;
            color: var(--text-dark);
            max-width: 700px;
            margin: 0 auto 30px auto;
            opacity: 0.9;
        }

        /* Language Toggle Buttons */
        .lang-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 40px;
        }

        .lang-btn {
            background: white;
            border: 3px solid var(--primary-color);
            padding: 10px 24px;
            font-size: 1.1rem;
            font-weight: 700;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 6px 0px var(--primary-color);
            transition: var(--transition);
            color: var(--text-dark);
        }

        .lang-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 9px 0px var(--primary-color);
        }

        .lang-btn:active {
            transform: translateY(3px);
            box-shadow: 0 2px 0px var(--primary-color);
        }

        .lang-btn.active {
            background: var(--primary-color);
            color: white;
            box-shadow: 0 6px 0px var(--primary-hover);
            border-color: var(--primary-hover);
        }

        /* Search and Filter Section */
        .controls-container {
            max-width: 1000px;
            margin: 0 auto 40px auto;
            background: white;
            padding: 25px;
            border-radius: 25px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
            border: 4px dashed var(--secondary-color);
            display: flex;
            flex-direction: column;
            gap: 20px;
            align-items: center;
        }

        .search-wrapper {
            position: relative;
            width: 100%;
            max-width: 500px;
        }

        .search-bar {
            width: 100%;
            padding: 15px 25px 15px 50px;
            border: 3px solid #e2e8f0;
            border-radius: 50px;
            font-size: 1.1rem;
            font-family: inherit;
            outline: none;
            transition: var(--transition);
        }

        .search-bar:focus {
            border-color: var(--secondary-color);
            box-shadow: 0 0 15px rgba(132, 94, 247, 0.2);
        }

        .search-icon {
            position: absolute;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.3rem;
            pointer-events: none;
        }

        .filter-buttons {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 12px;
        }

        .filter-btn {
            background: #f8f9fa;
            border: 2px solid #e9ecef;
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
            font-family: inherit;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .filter-btn:hover {
            transform: scale(1.05);
            background: #e9ecef;
        }

        .filter-btn.active {
            background: var(--secondary-color);
            color: white;
            border-color: var(--secondary-color);
            box-shadow: 0 5px 15px rgba(132, 94, 247, 0.3);
        }

        .counter-badge {
            background: #f1f3f5;
            padding: 8px 18px;
            border-radius: 20px;
            font-weight: 700;
            color: var(--text-dark);
            border: 2px solid #e9ecef;
            font-size: 1rem;
        }

        /* Cat Grid */
        .cat-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Cat Card Styling with Cute Ears */
        .cat-card {
            background: white;
            border-radius: 30px;
            overflow: hidden;
            box-shadow: var(--card-shadow);
            border: 5px solid white;
            position: relative;
            transition: var(--transition);
            display: flex;
            flex-direction: column;
            margin-top: 15px;
            animation: fadeIn 0.5s ease;
        }

        .cat-card::before, .cat-card::after {
            content: '';
            position: absolute;
            top: -16px;
            width: 35px;
            height: 30px;
            background: white;
            border: 5px solid white;
            z-index: 1;
            transition: var(--transition);
        }
        
        .cat-card::before {
            left: 35px;
            border-top-left-radius: 70% 100%;
            border-top-right-radius: 30% 50%;
            transform: rotate(-15deg);
            box-shadow: -4px -4px 0 rgba(0,0,0,0.02);
        }

        .cat-card::after {
            right: 35px;
            border-top-right-radius: 70% 100%;
            border-top-left-radius: 30% 50%;
            transform: rotate(15deg);
            box-shadow: 4px -4px 0 rgba(0,0,0,0.02);
        }

        .ear-inner-l, .ear-inner-r {
            position: absolute;
            top: -10px;
            width: 18px;
            height: 18px;
            background: #ffb6c1;
            z-index: 2;
            pointer-events: none;
            border-radius: 50% 50% 0 0;
        }
        .ear-inner-l { left: 43px; transform: rotate(-15deg); }
        .ear-inner-r { right: 43px; transform: rotate(15deg); }

        .cat-card:hover {
            transform: translateY(-10px) scale(1.01);
            box-shadow: 0 20px 40px rgba(255, 111, 145, 0.25);
        }

        .cat-img-wrapper {
            position: relative;
            height: 240px;
            overflow: hidden;
            background: #f0f0f0;
        }

        .cat-img-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .cat-card:hover .cat-img-wrapper img {
            transform: scale(1.1);
        }

        .category-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: rgba(255, 255, 255, 0.95);
            padding: 6px 12px;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 700;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
            gap: 5px;
            z-index: 5;
        }

        .cat-info {
            padding: 25px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .cat-name {
            font-size: 1.6rem;
            color: var(--secondary-color);
            margin-bottom: 10px;
        }

        .cat-desc {
            font-size: 1rem;
            color: #576574;
            line-height: 1.5;
            margin-bottom: 15px;
            flex-grow: 1;
        }

        .tag-container {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 20px;
        }

        .personality-tag {
            font-size: 0.85rem;
            padding: 4px 10px;
            border-radius: 12px;
            font-weight: 600;
        }

        .tag-0 { background: #ffe3e3; color: #ff6b6b; }
        .tag-1 { background: #e3faf2; color: #0ca678; }
        .tag-2 { background: #e8f7ff; color: #1c7ed6; }

        /* Speech Bubble style for Fun Facts */
        .fact-bubble {
            background: #fff9db;
            border: 2px solid #ffe066;
            border-radius: 18px;
            padding: 15px;
            margin-bottom: 20px;
            position: relative;
            font-size: 0.95rem;
            color: #744210;
        }

        .fact-bubble::before {
            content: '💡 Did you know?';
            display: block;
            font-weight: 700;
            margin-bottom: 5px;
            font-size: 0.9rem;
            color: #f59f00;
        }

        .card-actions {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            margin-top: auto;
        }

        .card-btn {
            border: none;
            padding: 12px 10px;
            font-family: inherit;
            font-weight: 700;
            font-size: 0.95rem;
            border-radius: 15px;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 5px;
        }

        .btn-sound {
            background: var(--primary-color);
            color: white;
            box-shadow: 0 4px 0 #d9486b;
        }

        .btn-sound:hover {
            transform: translateY(-2px);
            background: var(--primary-hover);
            box-shadow: 0 6px 0 #d9486b;
        }

        .btn-sound:active {
            transform: translateY(2px);
            box-shadow: 0 1px 0 #d9486b;
        }

        .btn-stats {
            background: #e2e8f0;
            color: var(--text-dark);
            box-shadow: 0 4px 0 #cbd5e1;
        }

        .btn-stats:hover {
            transform: translateY(-2px);
            background: #cbd5e1;
            box-shadow: 0 6px 0 #94a3b8;
        }

        .btn-stats:active {
            transform: translateY(2px);
            box-shadow: 0 1px 0 #cbd5e1;
        }

        /* Stats Sliding Drawer overlay */
        .stats-drawer {
            position: absolute;
            bottom: -100%;
            left: 0;
            width: 100%;
            background: var(--secondary-color);
            color: white;
            padding: 25px;
            border-top-left-radius: 25px;
            border-top-right-radius: 25px;
            transition: var(--transition);
            z-index: 10;
            box-shadow: 0 -10px 20px rgba(0,0,0,0.1);
        }

        .stats-drawer.open {
            bottom: 0;
        }

        .stats-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            border-bottom: 2px dashed rgba(255,255,255,0.3);
            padding-bottom: 8px;
        }

        .close-stats {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            font-weight: bold;
        }

        .stat-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 1.1rem;
        }

        .stat-label {
            opacity: 0.85;
            font-weight: 600;
        }

        .stat-val {
            font-weight: 700;
        }

        /* Pagination Load More Button */
        .pagination-container {
            text-align: center;
            margin: 40px auto;
        }

        .btn-loadmore {
            background: var(--secondary-color);
            color: white;
            border: none;
            padding: 15px 35px;
            font-size: 1.2rem;
            font-family: inherit;
            font-weight: 700;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 6px 0 #5f3dc4;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .btn-loadmore:hover {
            background: #7048e8;
            box-shadow: 0 8px 0 #5f3dc4;
            transform: translateY(-2px);
        }

        .btn-loadmore:active {
            transform: translateY(4px);
            box-shadow: 0 2px 0 #5f3dc4;
        }

        /* Quiz Box */
        .quiz-section {
            max-width: 800px;
            margin: 60px auto 40px auto;
            background: white;
            border-radius: 35px;
            padding: 40px;
            box-shadow: 0 20px 50px rgba(132,94,247,0.15);
            border: 8px solid #f3f0ff;
            text-align: center;
            position: relative;
        }

        .quiz-section::before {
            content: '✏️';
            position: absolute;
            top: -25px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 2.5rem;
            background: white;
            padding: 5px 15px;
            border-radius: 50%;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        .quiz-title {
            color: var(--secondary-color);
            font-size: 2.2rem;
            margin-bottom: 10px;
        }

        .quiz-desc {
            font-size: 1.1rem;
            color: #576574;
            margin-bottom: 30px;
        }

        .score-board {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            font-size: 1.3rem;
            font-weight: 700;
            background: #f3f0ff;
            padding: 12px 25px;
            border-radius: 50px;
            width: fit-content;
            margin: 0 auto 30px auto;
            color: var(--secondary-color);
            border: 3px solid #dcd3ff;
        }

        .question-card {
            background: #faf9ff;
            border-radius: 20px;
            padding: 30px;
            border: 2px solid #eee;
            margin-bottom: 35px;
            min-height: 180px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
            font-weight: 600;
            line-height: 1.4;
        }

        .options-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        @media (max-width: 600px) {
            .options-grid { grid-template-columns: 1fr; }
            h1 { font-size: 2.2rem; }
        }

        .option-btn {
            background: white;
            border: 3px solid #e2e8f0;
            padding: 18px 20px;
            font-family: inherit;
            font-size: 1.1rem;
            font-weight: 700;
            border-radius: 20px;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 6px 0 #e2e8f0;
            color: var(--text-dark);
        }

        .option-btn:hover:not(:disabled) {
            border-color: var(--secondary-color);
            box-shadow: 0 6px 0 var(--secondary-color);
            transform: translateY(-2px);
        }

        .option-btn:active:not(:disabled) {
            transform: translateY(4px);
            box-shadow: 0 2px 0 var(--secondary-color);
        }

        .option-btn.correct {
            background: #c2f970;
            border-color: #92d03a;
            box-shadow: 0 6px 0 #7aa82f;
            color: #2b5c00;
        }

        .option-btn.incorrect {
            background: #ffccd5;
            border-color: #ff8787;
            box-shadow: 0 6px 0 #fa5252;
            color: #c91a1a;
        }

        .quiz-success {
            display: none;
            padding: 40px 10px;
            animation: zoomIn 0.5s ease;
        }

        .quiz-success h3 {
            font-size: 2.4rem;
            color: #40c057;
            margin-bottom: 15px;
        }

        .quiz-success p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            color: #576574;
        }

        .btn-restart {
            background: var(--secondary-color);
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.2rem;
            font-family: inherit;
            font-weight: 700;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 6px 0 #5f3dc4;
            transition: var(--transition);
        }

        .btn-restart:hover {
            background: #7048e8;
            box-shadow: 0 8px 0 #5f3dc4;
            transform: translateY(-2px);
        }

        .btn-restart:active {
            transform: translateY(4px);
            box-shadow: 0 2px 0 #5f3dc4;
        }

        /* Floating Helper Cat */
        .helper-cat {
            position: fixed;
            bottom: 25px;
            right: 25px;
            z-index: 100;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: flex-end;
        }

        .helper-cat:hover {
            transform: translateY(-5px) scale(1.05);
        }

        .cat-avatar {
            font-size: 3.5rem;
            background: white;
            border: 4px solid var(--primary-color);
            border-radius: 50%;
            width: 75px;
            height: 75px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 10px 25px rgba(255,111,145,0.3);
            position: relative;
        }

        .cat-avatar::after {
            content: '💬';
            position: absolute;
            top: -5px;
            right: -5px;
            font-size: 1.2rem;
        }

        .chat-bubble {
            background: white;
            border: 3px solid var(--primary-color);
            border-radius: 20px;
            padding: 15px 20px;
            margin-right: 15px;
            max-width: 250px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            position: relative;
            display: none;
            animation: fadeIn 0.4s ease;
        }

        .chat-bubble::after {
            content: '';
            position: absolute;
            right: -12px;
            bottom: 20px;
            border-width: 12px 0 12px 12px;
            border-style: solid;
            border-color: transparent transparent transparent white;
            display: block;
            width: 0;
            z-index: 2;
        }

        .chat-bubble::before {
            content: '';
            position: absolute;
            right: -16px;
            bottom: 18px;
            border-width: 14px 0 14px 14px;
            border-style: solid;
            border-color: transparent transparent transparent var(--primary-color);
            display: block;
            width: 0;
            z-index: 1;
        }

        footer {
            text-align: center;
            margin-top: 50px;
            color: #8b9bb4;
            font-size: 0.95rem;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes zoomIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }

        @keyframes bounceIn {
            0% { opacity: 0; transform: scale(0.3); }
            50% { opacity: 0.9; transform: scale(1.1); }
            70% { transform: scale(0.9); }
            100% { opacity: 1; transform: scale(1); }
        }

        .no-results {
            grid-column: 1 / -1;
            text-align: center;
            padding: 50px 20px;
            font-size: 1.3rem;
            color: #576574;
            display: none;
        }
    </style>
</head>
<body>

    <div class="ambient-bg" id="ambientBg"></div>

    <header>
        <div class="header-content">
            <div class="hero-img-container" id="heroImageContainer">
                <img src="kids_cat_world_hero.png" alt="Kids' Cat World Hero Banner" onerror="this.src='https://images.unsplash.com/photo-1548247416-ec66f4900b2e?auto=format&fit=crop&w=800&q=80'">
            </div>
            <h1 id="ui-title">Kids' Cat World</h1>
            <p class="subtitle" id="ui-subtitle">Discover, learn, and hear different cats from all around the world!</p>
        </div>
    </header>

    <!-- Language Buttons -->
    <div class="lang-container">
        <button class="lang-btn active" onclick="switchLanguage('en')">🇬🇧 English</button>
        <button class="lang-btn" onclick="switchLanguage('si')">🇱🇰 සිංහල</button>
        <button class="lang-btn" onclick="switchLanguage('ta')">🇱🇰 தமிழ்</button>
    </div>

    <!-- Filter Tools -->
    <div class="controls-container">
        <div class="search-wrapper">
            <span class="search-icon">🔍</span>
            <input type="text" class="search-bar" id="searchBar" placeholder="Search for a cat..." oninput="filterCats()">
        </div>
        <div class="filter-buttons">
            <button class="filter-btn active" id="btn-all" onclick="filterCategory('all')">🐱 <span id="ui-all">All Cats</span></button>
            <button class="filter-btn" id="btn-fluffy" onclick="filterCategory('fluffy')">☁️ <span id="ui-fluffy">Fluffy</span></button>
            <button class="filter-btn" id="btn-playful" onclick="filterCategory('playful')">⚡ <span id="ui-playful">Playful</span></button>
            <button class="filter-btn" id="btn-wild" onclick="filterCategory('wild')">🦁 <span id="ui-wild">Wild</span></button>
            <button class="filter-btn" id="btn-fantasy" onclick="filterCategory('fantasy')">✨ <span id="ui-fantasy">Fantasy</span></button>
        </div>
        <div class="counter-badge" id="counterBadge">Showing 0 of 0 cats</div>
    </div>

    <!-- Main Cat Cards Grid -->
    <div class="cat-grid" id="catGrid"></div>

    <div class="no-results" id="noResults">
        😿 No cats found! Try another name.
    </div>

    <div class="pagination-container" id="paginationContainer">
        <button class="btn-loadmore" onclick="loadMoreCats()">🐾 <span id="ui-loadmore">Load More Cats</span> 🐾</button>
    </div>

    <!-- Knowledge Quiz Game -->
    <div class="quiz-section">
        <h2 class="quiz-title" id="ui-quiz-title">Cat Quiz Challenge!</h2>
        <p class="quiz-desc" id="ui-quiz-desc">Test your feline knowledge and earn paw points!</p>
        
        <div class="score-board">
            🐾 <span id="ui-score-label">Score</span>: <span id="score">0</span> / 5
        </div>

        <div id="quiz-play-area">
            <div class="question-card" id="questionCard"></div>
            <div class="options-grid" id="optionsGrid"></div>
        </div>

        <div class="quiz-success" id="quizSuccess">
            <h3 id="ui-success-title">🎉 Purr-fect Score!</h3>
            <p id="ui-success-desc">You are a certified Cat Expert! Meow-tastic job!</p>
            <button class="btn-restart" onclick="restartQuiz()" id="ui-restart-btn">Play Again 🔄</button>
        </div>
    </div>

    <!-- Helper Widget with Jokes -->
    <div class="helper-cat" onclick="toggleChatBubble()">
        <div class="chat-bubble" id="chatBubble">
            Hello, little friend! Click me to hear a funny cat joke!
        </div>
        <div class="cat-avatar">🐱</div>
    </div>

    <footer>
        <p>© 2026 Kids' Cat World. Designed with ❤️ for future animal lovers.</p>
    </footer>

    <script>
        // Language State
        let currentLang = 'en';

        // Translation Maps
        const uiTranslations = {
            en: {
                title: "Kids' Cat World 🐱",
                subtitle: "Discover, learn, and hear different cats from all around the world!",
                searchPlaceholder: "Search for a cat...",
                all: "All Cats",
                fluffy: "Fluffy Cats ☁️",
                playful: "Playful Cats ⚡",
                wild: "Wild Cats 🦁",
                fantasy: "Fantasy Cats ✨",
                btnHear: "Hear Sound! 🔊",
                btnStats: "Stats 📊",
                quizTitle: "Cat Quiz Challenge! ✏️",
                quizDesc: "Test your feline knowledge and earn paw points!",
                scoreLabel: "Score",
                successTitle: "🎉 Purr-fect Score!",
                successDesc: "You are a certified Cat Expert! Meow-tastic job!",
                restartBtn: "Play Again 🔄",
                noResults: "😿 No cats found! Try another name.",
                statsSize: "Size",
                statsLife: "Lifespan",
                close: "Close ❌",
                helperIntro: "Hello! Click me to read a funny cat joke!",
                loadMore: "Load More Cats",
                showingLabel: "Showing {show} of {total} Cats",
                jokes: [
                    "Why did the cat sit on the computer? To keep an eye on the mouse! 🐭",
                    "What is a cat's favorite color? Purrr-ple! 💜",
                    "What do you call a pile of kittens? A meow-ntain! ⛰️",
                    "Why was the cat sitting on the clock? He wanted to be a cool cat on time! ⏰",
                    "What is a cat's favorite school subject? MEOW-thematics! 📐"
                ]
            },
            si: {
                title: "ළමා පූස් ලෝකය 🐱",
                subtitle: "ලොව පුරා වෙසෙන විවිධ පූස් වර්ග ගැන ඉගෙන ගන්න, ඔවුන්ගේ හඬට සවන් දෙන්න!",
                searchPlaceholder: "පූසෙක් සොයන්න...",
                all: "සියලුම පූසන්",
                fluffy: "ලොම් බහුල ☁️",
                playful: "දඟකාර ⚡",
                wild: "කැලෑ බළලුන් 🦁",
                fantasy: "මනඃකල්පිත ✨",
                btnHear: "හඬ අසන්න! 🔊",
                btnStats: "විස්තර 📊",
                quizTitle: "පූස් දැනුම මිනුම! ✏️",
                quizDesc: "පූසන් ගැන ඔබේ දැනුම පරීක්ෂා කර ලකුණු ලබා ගන්න!",
                scoreLabel: "ලකුණු",
                successTitle: "🎉 විශිෂ්ටයි! උපරිම ලකුණු!",
                successDesc: "ඔබ දැන් පූස් විශේෂඥයෙක්! ඔබට මියාව් ස්තුතියි!",
                restartBtn: "නැවත ක්‍රීඩා කරන්න 🔄",
                noResults: "😿 පූසන් හමු වූයේ නැත! වෙනත් නමක් සොයන්න.",
                statsSize: "ප්‍රමාණය",
                statsLife: "ආයු කාලය",
                close: "වහන්න ❌",
                helperIntro: "ආයුබෝවන් යහළුවා! පූස් විහිළුවක් කියවන්න මාව ක්ලික් කරන්න!",
                loadMore: "තවත් පූසන් පෙන්වන්න",
                showingLabel: "පූසන් {total} කින් {show} දෙනෙකු පෙන්වයි",
                jokes: [
                    "පූසෝ පරිගණකය උඩ වාඩි වෙන්නේ ඇයි? මීයා (mouse) දිහා බලාගෙන ඉන්න! 🐭",
                    "පූසන් කැමතිම පාට මොකක්ද? පර්පල් (Purrr-ple) පාට! 💜",
                    "පූස් පැටව් ගොඩකට ඉංග්‍රීසියෙන් කියන්නේ මොකක්ද? මියාවුන්ටන් (meow-ntain)! ⛰️",
                    "පූසා ඔරලෝසුව උඩ වාඩි වෙලා හිටියේ ඇයි? වෙලාවට වැඩ කරන පූසෙක් වෙන්න! ⏰",
                    "පූසන් පාසලේ ඉගෙන ගන්න කැමතිම විෂය මොකක්ද? මියාව් ගණිතය (MEOW-thematics)! 📐"
                ]
            },
            ta: {
                title: "குழந்தைகளின் பூனை உலகம் 🐱",
                subtitle: "உலகெங்கிலும் உள்ள பல்வேறு பூனை இனங்களைக் கற்றுக் கொள்ளவும், அவற்றின் ஒலியைக் கேட்கவும்!",
                searchPlaceholder: "பூனையைத் தேடுங்கள்...",
                all: "அனைத்து பூனைகள்",
                fluffy: "அடர்ந்த முடிகள் ☁️",
                playful: "துறுதுறுப்பானவை ⚡",
                wild: "காட்டு பூனைகள் 🦁",
                fantasy: "மாயாஜாலம் ✨",
                btnHear: "ஒலியைக் கேள்! 🔊",
                btnStats: "விவரம் 📊",
                quizTitle: "பூனை வினாடி வினா! ✏️",
                quizDesc: "பூனைகள் பற்றிய உங்களது அறிவைச் சோதித்து புள்ளிகளைப் பெறுங்கள்!",
                scoreLabel: "புள்ளிகள்",
                successTitle: "🎉 அருமை! முழு மதிப்பெண்கள்!",
                successDesc: "நீங்கள் இப்போது ஒரு பூனை நிபுணர்! பாராட்டுகள்!",
                restartBtn: "மீண்டும் விளையாடு 🔄",
                noResults: "😿 பூனைகள் எதுவும் கிடைக்கவில்லை! வேறு பெயரைத் தேடுங்கள்.",
                statsSize: "அளவு",
                statsLife: "ஆயுட்காலம்",
                close: "மூடு ❌",
                helperIntro: "வணக்கம் நண்பரே! பூனை பற்றிய ஜோக் கேட்க என்னை கிளிக் செய்யவும்!",
                loadMore: "மேலும் பூனைகளைக் காட்டு",
                showingLabel: "மொத்தம் {total} பூனைகளில் {show} காட்டப்படுகின்றன",
                jokes: [
                    "பூனை ஏன் கணினி மீது அமர்ந்திருக்கிறது? மவுஸ் (Mouse) மீது கண் வைக்க! 🐭",
                    "பூனைகளுக்கு பிடித்த நிறம் எது? பர்பிள் (Purrr-ple)! 💜",
                    "பூனைக்குட்டிகளின் கூட்டத்திற்கு என்ன பெயர்? மியாவ்-ண்டைன் (meow-ntain)! ⛰️",
                    "பூனை ஏன் கடிகாரத்தின் மீது அமர்ந்திருந்தது? சரியான நேரத்தை காட்ட! ⏰",
                    "பூனைகளுக்கு பிடித்த பள்ளி பாடம் எது? மியாவ்-கணிதம் (MEOW-thematics)! 📐"
                ]
            }
        };

        // Grammar property translation dictionaries
        const dictSizes = {
            small: { en: "small", si: "කුඩා", ta: "சிறிய" },
            medium: { en: "medium-sized", si: "මධ්‍යම ප්‍රමාණයේ", ta: "நடுத்தர" },
            large: { en: "large", si: "විශාල", ta: "பெரிய" },
            huge: { en: "huge", si: "යෝධ", ta: "மிகப் பெரிய" }
        };

        const dictOrigins = {
            persia: { en: "ancient Persia", si: "පැරණි පර්සියාවෙන්", ta: "பண்டைய பாரசீகத்திலிருந்து" },
            thailand: { en: "Thailand", si: "තායිලන්තයෙන්", ta: "தாய்லாந்திலிருந்து" },
            usa: { en: "the United States", si: "ඇමරිකා එක්සත් ජනපදයෙන්", ta: "அமெரிக்காவிலிருந்து" },
            egypt: { en: "Egypt", si: "ඊජිප්තුවෙන්", ta: "எகிப்திலிருந்து" },
            scotland: { en: "Scotland", si: "ස්කොට්ලන්තයෙන්", ta: "ஸ்காட்லாந்திலிருந்து" },
            wild: { en: "the wild grasslands", si: "වන තණබිම් වලින්", ta: "காட்டுப் புல்வெளிகளில் இருந்து" },
            jungle: { en: "the jungle", si: "කැලෑවෙන්", ta: "காடுகளில் இருந்து" },
            space: { en: "outer space", si: "ඈත අභ්‍යවකාශයෙන්", ta: "விண்வெளியில் இருந்து" },
            japan: { en: "Japan", si: "ජපානයෙන්", ta: "ஜப்பானில் இருந்து" },
            france: { en: "France", si: "ප්‍රංශයෙන්", ta: "பிரான்சிலிருந்து" },
            russia: { en: "Russia", si: "රුසියාවෙන්", ta: "ரஷ்யாவிலிருந்து" },
            turkey: { en: "Turkey", si: "තුර්කියෙන්", ta: "துருக்கியில் இருந்து" },
            uk: { en: "the United Kingdom", si: "එක්සත් රාජධානියෙන්", ta: "பிரித்தானியாவிலிருந்து" },
            canada: { en: "Canada", si: "කැනඩාවෙන්", ta: "கனடாவிலிருந்து" },
            norway: { en: "Norway", si: "නෝර්වේ රාජ්‍යයෙන්", ta: "நார்வேயில் இருந்து" },
            china: { en: "China", si: "චීනයෙන්", ta: "சீனாவிலிருந்து" },
            abyssinia: { en: "Abyssinia (Ethiopia)", si: "අබිසීනියාවෙන් (ඉතියෝපියාවෙන්)", ta: "அபிசீனியாவிலிருந்து (எத்தியோப்பியா)" },
            brazil: { en: "Brazil", si: "බ්‍රසීලයෙන්", ta: "பிரேசிலில் இருந்து" },
            oceania: { en: "islands of Oceania", si: "ඕෂනියා දූපත් වලින්", ta: "ஓசியானியா தீவுகளில் இருந்து" },
            asia: { en: "Asia", si: "ආසියාවෙන්", ta: "ஆசியாவிலிருந்து" },
            africa: { en: "Africa", si: "අප්‍රිකාවෙන්", ta: "ஆப்பிரிக்காவிலிருந்து" },
            ocean: { en: "the deep blue ocean", si: "ගැඹුරු නිල් සාගරයෙන්", ta: "ஆழ்கடலில் இருந்து" },
            dreamland: { en: "Dreamland", si: "සිහින ලෝකයෙන්", ta: "கனவுலகில் இருந்து" },
            unknown: { en: "unknown lands", si: "නොදන්නා දේශයකින්", ta: "அறியப்படாத தேசத்தில் இருந்து" }
        };

        const dictChars = {
            vocal: { en: "talkative", si: "කතාබහට ලැදි", ta: "பேசும் குணம் கொண்ட" },
            friendly: { en: "friendly", si: "මිත්‍රශීලී", ta: "அன்பான" },
            active: { en: "active", si: "ක්‍රියාශීලී", ta: "சுறுசுறுப்பான" },
            gentle: { en: "gentle", si: "මෘදු", ta: "மென்மையான" },
            calm: { en: "calm", si: "සන්සුන්", ta: "அமைதியான" },
            smart: { en: "smart", si: "බුද්ධිමත්", ta: "புத்திசாலித்தனமான" },
            brave: { en: "brave", si: "නිර්භීත", ta: "தைரியமான" },
            curious: { en: "curious", si: "කුතුහලයෙන් පිරි", ta: "ஆர்வமிக்க" },
            fast: { en: "fast", si: "වේගවත්", ta: "வேகமான" },
            sleepy: { en: "sleepy", si: "නිදිමත", ta: "அதிகம் தூங்கும்" },
            loyal: { en: "loyal", si: "ලැදියා ඇති", ta: "விசுவாசமான" },
            magical: { en: "magical", si: "මායාවී", ta: "மந்திர சக்தி கொண்ட" },
            funny: { en: "funny", si: "විනෝදකාමී", ta: "வேடிக்கையான" },
            quiet: { en: "quiet", si: "නිහඬ", ta: "சத்தமில்லாத" },
            strong: { en: "strong", si: "ශක්තිමත්", ta: "வலிமையான" },
            sneaky: { en: "sneaky", si: "රහසිගත", ta: "தந்திரமான" },
            agile: { en: "agile", si: "වේගයෙන් පැනිය හැකි", ta: "விரைவாகத் தாவக்கூடிய" },
            sweet: { en: "sweet", si: "ලයාන්විත", ta: "இனிமையான" }
        };

        const dictFurs = {
            fluffy: { en: "long, fluffy", si: "දිගු සිනිඳු", ta: "நீளமான பஞ்சுபோன்ற" },
            short: { en: "short, smooth", si: "කෙටි සුමට", ta: "மென்மையான குட்டையான" },
            hairless: { en: "warm, hairless", si: "ලොම් නැති උණුසුම්", ta: "முடியில்லாத மிதமான சூடான" },
            spotted: { en: "spotted", si: "ලප සහිත", ta: "புள்ளிகள் கொண்ட" },
            striped: { en: "striped", si: "ඉරි සහිත", ta: "வரிகள் கொண்ட" },
            metallic: { en: "shiny metallic", si: "දිලිසෙන ලෝහමය", ta: "மின்னும் உலோக" },
            rainbow: { en: "rainbow-colored", si: "දේදුනු වර්ණැති", ta: "வானவில் நிற" },
            curly: { en: "curly-haired", si: "රැලි සහිත", ta: "சுருள் முடி" }
        };

        const dictActions = {
            lap: { en: "snuggle in your lap", si: "ඔබේ උකුලේ තුරුළු වීමට", ta: "உங்கள் மடியில் உறங்க" },
            play: { en: "chase toy mice", si: "සෙල්ලම් බඩු පස්සේ පන්නන්න", ta: "விளையாட்டு எலிகளைத் துரத்த" },
            jump: { en: "jump high on shelves", si: "ඉහළ රාක්ක වලට පැනීමට", ta: "உயரமான அலமாரிகளில் தாவ" },
            swim: { en: "splash and play in water", si: "වතුරේ සෙල්ලම් කිරීමට සහ පිහිනීමට", ta: "நீரில் விளையாடி நீந்த" },
            hunt: { en: "hunt and run in grasslands", si: "තණබිම් වල දිව යාමට", ta: "புல்வெளிகளில் ஓடி வேட்டையாட" },
            climb: { en: "climb the tallest trees", si: "උස ගස් නැගීමට", ta: "உயரமான மரங்களில் ஏற" },
            sleep: { en: "sleep all day in warm spots", si: "දවස පුරා උණුසුම් තැන්වල නිදා ගැනීමට", ta: "நாள் முழுவதும் வெயிலில் தூங்க" },
            fly: { en: "fly high in the clouds", si: "වලාකුළු අතර පියාසර කිරීමට", ta: "மேகங்களுக்கு மேலே பறக்க" },
            compute: { en: "play computer games", si: "පරිගණක ක්‍රීඩා කිරීමට", ta: "கணினி விளையாட்டுகள் விளையாட" },
            bake: { en: "bake delicious cupcakes", si: "රසවත් කප්කේක් සෑදීමට", ta: "சுவையான கேக்குகள் செய்ய" },
            explore: { en: "explore hidden treasures", si: "සැඟවුණු නිදන් සෙවීමට", ta: "புதையல்களைத் தேட" }
        };

        const dictFunFacts = {
            persian: {
                en: "They have been companion pets for thousands of years, starting in ancient Persia!",
                si: "ඔවුන් වසර දහස් ගණනක සිට පැරණි පර්සියාවෙන් (ඉරානයෙන්) පැවත එන සුරතලුන් කොට්ඨාසයකි!",
                ta: "இவை பழங்கால பாரசீக நாட்டில் (ஈரான்) இருந்து தோன்றி, ஆயிரக்கணக்கான ஆண்டுகளாக செல்லப்பிராணிகளாக உள்ளன!"
            },
            siamese: {
                en: "Siamese kittens are born completely white and get their dark patches as they grow older!",
                si: "සියම් පැටවුන් උපදින විට සම්පූර්ණයෙන්ම සුදු පාට වන අතර ඔවුන් වැඩෙන විට අඳුරු ලප ඇති වේ!",
                ta: "சியாமிய பூனைக்குட்டிகள் பிறக்கும் போது முற்றிலும் வெள்ளை நிறத்தில் பிறக்கின்றன, வளர வளரவே நிறம் மாறுகிறது!"
            },
            maine_coon: {
                en: "They have extra tufts of fur on their paws to help them walk on snow like natural snowshoes!",
                si: "හිම මත ඇවිදීමට උපකාර වන පරිදි ඔවුන්ගේ පාදවල අමතර ලොම් පිහිටා තිබේ!",
                ta: "பனியில் எளிதாக நடப்பதற்காக இவற்றின் பாதங்களில் கூடுதல் முடிகள் வளர்ந்துள்ளன!"
            },
            bengal: {
                en: "Unlike most domestic cats, Bengal cats absolutely love swimming and bathing in water!",
                si: "අනෙකුත් සුරතල් පූසන් මෙන් නොව, බෙංගාලි පූසන් වතුරේ නෑමට සහ පිහිනීමට බෙහෙවින් ප්‍රිය කරති!",
                ta: "மற்ற வீட்டு பூனைகளைப் போலல்லாமல், வங்காள பூனைகள் நீரில் குளிப்பதையும் நீந்துவதையும் மிகவும் விரும்புகின்றன!"
            },
            sphynx: {
                en: "Even though they have no fur, they need regular baths to keep their skin healthy!",
                si: "ලොම් නොතිබුණත්, ඔවුන්ගේ සංවේදී සම පිරිසිදුව තබා ගැනීමට ඔවුන්ව නිතර නාවන්නට සිදු වේ!",
                ta: "முடிகள் இல்லை என்றாலும், இவற்றின் சருமத்தைப் பாதுகாக்க வாரமொருமுறை குளிப்பாட்ட வேண்டும்!"
            },
            scottish: {
                en: "All Scottish Fold kittens are born with straight ears, and they only start to fold after 3 to 4 weeks!",
                si: "උපතේදී සියලුම පැටවුන්ට කෙලින් කන් පිහිටන අතර, සති 3-4 කට පසුව ඒවා නැමීමට පටන් ගනී!",
                ta: "இவை பிறக்கும் போது நேராக இருக்கும் காதுகள், 3 முதல் 4 வாரங்களுக்குப் பிறகே மடியத் தொடங்குகின்றன!"
            },
            lion: {
                en: "A lion's mighty roar can be heard from 5 miles (8 kilometers) away! It tells everyone who is boss!",
                si: "සිංහයෙකුගේ ගර්ජනාව සැතපුම් 5ක් (කිලෝමීටර් 8ක්) ඈතට ඇසෙන අතර එය කැලෑවේ තම බලය පෙන්වීමට යොදා ගනී!",
                ta: "சிங்கத்தின் கர்ஜனை 5 மைல் (8 கி.மீ) தூரம் வரை கேட்கும்! தான் காட்டின் ராஜா என்பதை இது பிற விலங்குகளுக்கு உணர்த்தும்!"
            },
            cheetah: {
                en: "Cheetahs cannot roar like lions; instead, they purr and chirp just like cute house cats!",
                si: "චීටාවන්ටසිංහයන් මෙන් ගර්ජනා කළ නොහැකි අතර, ඔවුන්ද නිවෙස්වල වෙසෙන පූසන් මෙන් මියාව් ශබ්ද නඟති!",
                ta: "சிறுத்தைகளால் சிங்கத்தைப் போல கர்ஜிக்க முடியாது; மாறாக இவை சாதாரண பூனைகளைப் போல மெல்லிய ஒலி மட்டுமே எழுப்பும்!"
            },
            tiger: {
                en: "No two tigers have the exact same stripes! Their stripes are unique like human fingerprints.",
                si: "කොටින් දෙදෙනෙකුට කිසිසේත්ම එකම ඉරි පිහිටීමක් නොමැත! ඒවා මිනිස් ඇඟිලි සලකුණු මෙන් අනන්‍ය වේ.",
                ta: "எந்த இரு புலிகளுக்கும் ஒரே மாதிரியான கோடுகள் இருப்பதில்லை! அவை மனித கைரேகை போல தனித்துவமானவை."
            },
            panther: {
                en: "Black panthers are not a separate breed; they are actually jaguars or leopards with black coats!",
                si: "කළු පැන්තර් යනු වෙනම විශේෂයක් නොවේ; ඔවුන් ඇත්ත වශයෙන්ම කළු පැහැති ජගුවර්ලා හෝ දිවියන් වේ!",
                ta: "கருஞ்சிறுத்தை என்பது தனி இனம் அல்ல; அவை உண்மையில் கருப்பு நிறமுள்ள ஜாகுவார் அல்லது சிறுத்தைகளே ஆகும்!"
            },
            robot: {
                en: "This cat doesn't eat fish; it runs on batteries and recharges when it takes a nap!",
                si: "මෙම බළලා මාළු කන්නේ නැත; ඔවුන් ක්‍රියාත්මක වන්නේ බැටරි වලින් වන අතර නිදාගන්නා විට රීචාජ් වේ!",
                ta: "இந்த பூனை மீன் சாப்பிடுவதில்லை; இது மின்கலங்கள் மூலம் இயங்குகிறது, தூங்கும் போது ரீசார்ஜ் ஆகும்!"
            },
            space: {
                en: "In space, this cat floats around chasing cosmic mouse-shaped satellites!",
                si: "අභ්‍යවකාශයේදී මෙම බළලා මී හැඩැති චන්ද්‍රිකා පසුපස පාවෙමින් හඹා යයි!",
                ta: "விண்வெளியில் இந்த பூனை எலி வடிவிலான செயற்கைக்கோள்களைத் துரத்திப் மிதக்கிறது!"
            },
            ninja: {
                en: "They move so quietly that even the mice can never hear them coming until it is too late!",
                si: "ඔවුන් කෙතරම් නිහඬව ගමන් කරන්නේද යත්, මීයන්ට ඔවුන් පැමිණෙන ශබ්දය කිසිසේත්ම ඇසෙන්නේ නැත!",
                ta: "இவை மிகவும் சத்தமில்லாமல் நகர்வதால், எலிகள் இவை வருவதை அறியவே முடியாது!"
            },
            chef: {
                en: "Their special recipe is tuna cake with milk frosting, and they never share the secret sauce!",
                si: "ඔවුන්ගේ විශේෂ වට්ටෝරුව වන්නේ කිරි ක්‍රීම් දැමූ ටූනා කේක් ය. ඔවුන් රහස් සෝස් වට්ටෝරුව පවසන්නේ නැත!",
                ta: "இவற்றின் சிறப்பு உணவு பால் கிரீம் கொண்ட டுனா கேக் ஆகும், ரகசிய சாஸை பகிர்ந்து கொள்ளாது!"
            },
            mermaid: {
                en: "Instead of back paws, they have a shiny fish tail and love to swim with dolphins!",
                si: "පසුපස පාද වෙනුවට ඔවුන්ට දිලිසෙන මාළු වලිගයක් ඇති අතර ඩොල්ෆින් සතුන් සමඟ පිහිනීමට ප්‍රිය කරති!",
                ta: "பின் கால்களுக்கு பதிலாக, இவற்றுக்கு மின்னும் மீன் வால் உள்ளது மற்றும் டால்பின்களுடன் நீந்த விரும்புகின்றன!"
            },
            wizard: {
                en: "With a wave of their magic wand, they can turn ordinary water into warm milk!",
                si: "ඔවුන්ගේ ඉන්ද්‍රජාලික සැරයටිය වැනීමෙන් සාමාන්‍ය ජලය උණුසුම් කිරි බවට පත් කළ හැකිය!",
                ta: "தங்கள் மந்திரக்கோலை அசைப்பதன் மூலம் சாதாரண நீரை சூடான பாலாக மாற்றும் சக்தி கொண்டவை!"
            },
            default: {
                en: "They are wonderful creatures that fill our world with happiness, soft purrs, and playful pounces!",
                si: "ඔවුන් අපේ ලෝකය සතුටින්, මෘදු හඬින් සහ දඟකාර සෙල්ලම් වලින් පුරවන අපූරු ජීවීන් කොට්ඨාසයකි!",
                ta: "இவை நம் உலகை மகிழ்ச்சியாலும், மென்மையான ஒலியாலும், விளையாட்டுத் தனத்தாலும் நிரப்பும் அருமையான விலங்குகள்!"
            }
        };

        const imgPoolDomestic = [
            "https://images.unsplash.com/photo-1514888286974-6c03e2ca1dba?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1573865526739-10659fec78a5?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1533738363-b7f9aef128ce?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1543466835-00a7907e9de1?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1577023311546-cdc07a8454c9?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1592194996308-7b43878e84a6?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1526336024174-e58f5cdd8e13?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1561948955-570b270e7c36?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1519052537078-e6302a4968d4?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1495360010541-f48722b34f7d?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1518791841217-8f162f1e1131?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1548247416-ec66f4900b2e?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1533743983669-94fa5c4338ec?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1529778873920-4da4926a72c2?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1574158622643-69d34d72650a?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1501820030026-ac830c25b290?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1583511655857-d19b40a7a54e?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1608848461950-0fe51dfc41cb?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1494256997604-768d1f608cac?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1511275539165-cc46b1ee8960?auto=format&fit=crop&w=600&q=80"
        ];

        const imgPoolWild = [
            "https://images.unsplash.com/photo-1546182990-dffeafbe841d?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1507666405895-422edf31e40d?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1534447677768-be436bb09401?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1456926631375-92c8ce872def?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1547036967-23d11aacaee0?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1518156677180-95a2893f3e9f?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1564349683136-77e08dba1ef7?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1518818419601-72c8673f5852?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1602491453631-e2a5ad90a131?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1504618223053-559bdef9dd5a?auto=format&fit=crop&w=600&q=80"
        ];

        const imgPoolFantasy = [
            "https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1500485035595-cbe6f645feb1?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1485827404703-89b55fcc595e?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1556910103-1c02745aae4d?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1518806118471-f28b20a1d79d?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1559827291-72ee739d0d9a?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1579783902614-a3fb3927b6a5?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1518531933037-91b2f5f229cc?auto=format&fit=crop&w=600&q=80",
            "https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?auto=format&fit=crop&w=600&q=80"
        ];

        // Compact Raw Cat Entries String (100 Entries)
        const rawCatsList = [
            "persian|fluffy|high|Persian Cat|පර්සියානු බළලා|பெர்சியன் பூனை|persia|medium|fluffy|calm|gentle|lap|persian|0",
            "siamese|playful|standard|Siamese Cat|සියම් බළලා|சியாமிய பூனை|thailand|medium|short|vocal|friendly|play|siamese|5",
            "maine_coon|fluffy|low|Maine Coon|මේන් කූන් බළලා|மைனே கூன் பூனை|usa|large|fluffy|gentle|smart|swim|maine_coon|3",
            "bengal|playful|high|Bengal Cat|බෙංගාලි බළලා|வங்காள பூனை|usa|large|spotted|active|curious|swim|bengal|4",
            "sphynx|playful|standard|Sphynx Cat|ස්පින්ක්ස් බළලා|ஸ்பின்க்ஸ் பூனை|egypt|medium|hairless|friendly|active|lap|sphynx|10",
            "scottish|fluffy|high|Scottish Fold|ස්කොටිෂ් ෆෝල්ඩ් බළලා|ஸகாட்டிஷ் மடிப்பு பூனை|scotland|medium|short|calm|friendly|lap|scottish|1",
            "abyssinian|playful|high|Abyssinian|අබිසීනියානු බළලා|அபிசீனிய பூனை|abyssinia|medium|short|active|curious|play|default|4",
            "ragdoll|fluffy|high|Ragdoll|රැග්ඩෝල් බළලා|ராக்டால் பூனை|usa|large|fluffy|calm|gentle|lap|default|14",
            "russian_blue|fluffy|standard|Russian Blue|රුසියානු නිල් බළලා|ரஷ்ய நீல பூனை|russia|medium|short|quiet|calm|play|default|16",
            "british_shorthair|fluffy|standard|British Shorthair|බ්‍රිතාන්‍ය කෙටිලොම් බළලා|பிரிட்டிஷ் ஷார்ட்ஹேர்|uk|medium|short|calm|gentle|sleep|default|2",
            "birman|fluffy|high|Birman Cat|බර්මන් බළලා|பிர்மன் பூனை|unknown|medium|fluffy|gentle|quiet|lap|default|11",
            "burmese|playful|standard|Burmese Cat|බුරුම බළලා|பர்மிய பூனை|thailand|medium|short|friendly|active|play|default|13",
            "bombay|playful|standard|Bombay Cat|බොම්බේ බළලා|பம்பாய் பூனை|usa|medium|short|active|smart|play|default|12",
            "chartreux|fluffy|standard|Chartreux|ශාට්‍රියු බළලා|சார்ட்ரூක්ஸ் பூனை|france|medium|short|calm|quiet|sleep|default|17",
            "cornish_rex|playful|high|Cornish Rex|කෝනිෂ් රෙක්ස් බළලා|கார்னிஷ் ரெக்ஸ்|uk|medium|short|active|playful|jump|default|18",
            "devon_rex|playful|high|Devon Rex|ඩෙවොන් රෙක්ස් බළලා|டெவோன் ரெக்ஸ்|uk|medium|short|active|playful|jump|default|15",
            "egyptian_mau|playful|high|Egyptian Mau|ඊජිප්තු මාවු බළලා|எகிப்திய மாவ்|egypt|medium|spotted|active|fast|jump|default|19",
            "japanese_bobtail|playful|standard|Japanese Bobtail|ජපන් බොබ්ටේල් බළලා|ஜப்பானிய பாப்டெயில்|japan|medium|short|active|smart|play|default|7",
            "korat|fluffy|standard|Korat Cat|කොරට් බළලා|கோராட் பூனை|thailand|medium|short|quiet|gentle|lap|default|8",
            "manx|playful|standard|Manx Cat|මැන්ක්ස් බළලා|மேங்க்ஸ் பூனை|uk|medium|short|active|friendly|jump|default|6",
            "norwegian|fluffy|low|Norwegian Forest Cat|නෝර්වීජියානු වනාන්තර බළලා|நார்வே காடு பூனை|norway|large|fluffy|active|strong|climb|default|10",
            "ocicat|playful|standard|Ocicat|ඔසිසැට් බළලා|ஓசிகாட் பூனை|usa|large|spotted|active|smart|play|default|11",
            "ragamuffin|fluffy|high|Ragamuffin|රැගමෆින් බළලා|ராகாமுஃபின் பூனை|usa|large|fluffy|gentle|friendly|lap|default|12",
            "selkirk_rex|fluffy|standard|Selkirk Rex|සෙල්කර්ක් රෙක්ස් බළලා|சில்கிர்க் ரெக்ஸ்|usa|medium|curly|quiet|gentle|lap|default|13",
            "siberian|fluffy|low|Siberian Cat|සයිබීරියානු බළලා|சைபீரிய பூனை|russia|large|fluffy|active|strong|jump|default|14",
            "somali|fluffy|high|Somali Cat|සෝමාලි බළලා|சோமாலி பூனை|unknown|medium|fluffy|active|curious|play|default|15",
            "tonkinese|playful|standard|Tonkinese|ටොන්කිනීස් බළලා|டோங்கினீஸ் பூனை|canada|medium|short|vocal|friendly|play|default|16",
            "turkish_angora|fluffy|high|Turkish Angora|තුර්කි ඇන්ගෝරා බළලා|துருக்கிய அங்கோரா|turkey|medium|fluffy|active|smart|jump|default|17",
            "turkish_van|playful|standard|Turkish Van|තුර්කි වෑන් බළලා|துருக்கிய வான் பூனை|turkey|large|fluffy|active|swim|swim|default|18",
            "american_shorthair|fluffy|standard|American Shorthair|ඇමරිකානු කෙටිලොම් බළලා|அமெரிக்க ஷார்ட்ஹேர்|usa|medium|short|calm|friendly|play|default|19",
            "singapura|playful|high|Singapura|සිංගප්පූරු බළලා|சிங்கப்பூரா பூனை|unknown|small|short|active|playful|jump|default|9",
            "snowshoe|playful|standard|Snowshoe Cat|ස්නෝෂූ බළලා|ஸ்னோஷூ பூனை|usa|medium|short|friendly|vocal|play|default|3",
            "american_curl|fluffy|high|American Curl|ඇමරිකානු කර්ල් බළලා|அமெரிக்க கர்ல் பூனை|usa|medium|short|friendly|curious|play|default|4",
            "havana_brown|playful|standard|Havana Brown|හවානා බ්‍රවුන් බළලා|ஹவானா பிரவுன்|unknown|medium|short|active|curious|play|default|5",
            "laperm|fluffy|standard|LaPerm|ලැපර්ම් බළලා|லாபெர்ம் பூனை|usa|medium|curly|active|friendly|lap|default|6",
            "cymric|fluffy|standard|Cymric Cat|සිම්රික් බළලා|சிம்ரிக் பூனை|uk|large|fluffy|active|smart|jump|default|7",
            "nebelung|fluffy|standard|Nebelung|නෙබෙලුන්ග් බළලා|நெபெலுங் பூனை|russia|medium|fluffy|quiet|calm|lap|default|8",
            "peterbald|playful|standard|Peterbald|පීටර්බෝල්ඩ් බළලා|பீட்டர்பால்ட் பூனை|russia|medium|hairless|active|friendly|play|default|9",
            "savannah|playful|low|Savannah Cat|සවනා බළලා|சவன்னா பூனை|usa|large|spotted|active|strong|jump|default|0",
            "toyger|playful|standard|Toyger|ටොයිගර් බළලා|டாய்கர் பூனை|usa|medium|striped|active|smart|play|default|1",
            "chausie|playful|low|Chausie|චවුසි බළලා|சௌசி பூனை|egypt|large|short|active|brave|jump|default|2",
            "pixie_bob|fluffy|standard|Pixie-bob|පික්සි බොබ් බළලා|பிக்ஸி பாப் பூனை|usa|large|short|friendly|loyal|play|default|3",
            "serengeti|playful|standard|Serengeti|සෙරෙන්ගෙටි බළලා|செரெங்கெட்டி பூனை|usa|large|spotted|active|agile|jump|default|4",
            "burmilla|fluffy|standard|Burmilla|බර්මිලා බළලා|பர்மில்லா பூனை|uk|medium|short|calm|friendly|lap|default|5",
            "khao_manee|playful|high|Khao Manee|කාඕ මැනී බළලා|காவ் மானி பூனை|thailand|medium|short|active|curious|play|default|6",
            "lykoi|playful|standard|Lykoi (Wolf Cat)|ලයිකෝයි බළලා|லைகோய் ஓநாய் பூனை|usa|medium|short|active|smart|hunt|default|7",
            "minskin|playful|high|Minskin|මින්ස්කින් බළලා|மின்ஸ்கின் பூனை|usa|small|hairless|active|friendly|play|default|8",
            "munchkin|playful|high|Munchkin Cat|මුන්ච්කින් බළලා|முன்ச்கின் பூனை|usa|small|short|active|playful|play|default|9",
            "highlander|playful|standard|Highlander|හයිලෑන්ඩර් බළලා|ஹைலேண்டர் பூனை|usa|large|short|active|friendly|play|default|10",
            "korean_bobtail|playful|standard|Korean Bobtail|කොරියානු බොබ්ටේල් බළලා|கொரிய பாப்டெயில்|unknown|medium|short|active|smart|play|default|11",
            "american_wirehair|fluffy|standard|American Wirehair|ඇමරිකානු වයර්හෙයා බළලා|அமெரிக்க ஒயர்ஹேர்|usa|medium|short|calm|friendly|play|default|12",
            "australian_mist|playful|standard|Australian Mist|ඕස්ට්‍රේලියානු මිස්ට් බළලා|ஆஸ்திரேலிய මිஸ்ட்|unknown|medium|short|calm|friendly|lap|default|13",
            "brazilian_shorthair|playful|standard|Brazilian Shorthair|බ්‍රසීලියානු කෙටිලොම් බළලා|பிரேசிலியன் ஷார்ட்ஹேர்|brazil|medium|short|active|friendly|play|default|14",
            "chantilly_tiffany|fluffy|standard|Chantilly-Tiffany|චැන්ටිලි ටිෆනි බළලා|சாண்டிலி டிஃப்பனி|usa|medium|fluffy|gentle|quiet|lap|default|15",
            "cyprus_cat|playful|standard|Cyprus Cat|සයිප්‍රස් බළලා|சைப்ரஸ் பூனை|unknown|large|short|active|brave|climb|default|16",
            "don_skoy|playful|standard|Don Skoy|ඩොන් ස්කෝයි බළලා|டான் ஸ்காய் பூனை|russia|medium|hairless|active|friendly|play|default|17",
            "dwelf|playful|high|Dwelf Cat|ඩ්වෙල්ෆ් බළලා|டுவெல்ஃப் பூனை|usa|small|hairless|active|playful|play|default|18",
            "minskin_long|fluffy|high|Longhair Minskin|ලොම් සහිත මින්ස්කින්|மின்ஸ்கின் நீளமுடி|usa|small|fluffy|active|friendly|play|default|17",
            "kurilian_bobtail|fluffy|standard|Kurilian Bobtail|කුරිලියන් බොබ්ටේල් බළලා|குரிலியன் பாப்டெயில்|russia|large|fluffy|active|strong|swim|default|10",
            "sokoke|playful|standard|Sokoke Cat|සොකෝකේ බළලා|சோகோகே பூனை|unknown|medium|striped|active|curious|climb|default|11",

            // Wild Cats (61 - 80)
            "lion|wild|roar|Lion (King of Cats)|සිංහයා|சிங்கம்|wild|huge|fluffy|brave|strong|hunt|lion|0",
            "tiger|wild|roar|Tiger|ව්‍යාඝ්‍රයා|புலி|wild|huge|striped|brave|strong|swim|tiger|1",
            "cheetah|wild|purr|Cheetah|චීටා|சிறுத்தை|wild|large|spotted|fast|active|hunt|cheetah|2",
            "leopard|wild|roar|Leopard|දිවියා|சிறுத்தைப்புலி|jungle|large|spotted|strong|active|climb|default|3",
            "jaguar|wild|roar|Jaguar|ජගුවර්|ஜாகுவார்|jungle|large|spotted|strong|brave|swim|default|4",
            "snow_leopard|wild|roar|Snow Leopard|හිම දිවියා|பனிச் சிறுத்தை|wild|large|fluffy|quiet|brave|climb|default|8",
            "black_panther|wild|roar|Black Panther|කළු පැන්තර්|கருஞ்சிறுத்தை|jungle|large|short|quiet|sneaky|hunt|panther|9",
            "clouded_leopard|wild|roar|Clouded Leopard|වළාකුළු දිවියා|மேகமூட்ட சிறுத்தை|jungle|large|spotted|active|sneaky|climb|default|3",
            "cougar|wild|roar|Cougar (Puma)|කූගර් බළලා|பூமா பூனை|wild|large|short|strong|fast|jump|default|4",
            "lynx|wild|standard|Lynx|ලින්ක්ස් බළලා|லின்க்ஸ் காட்டுப்பூனை|wild|medium|fluffy|quiet|sneaky|hunt|default|7",
            "bobcat|wild|standard|Bobcat|බොබ්කැට් බළලා|பாப்கேட் பூனை|wild|medium|spotted|active|sneaky|hunt|default|7",
            "serval|wild|high|Serval Cat|සර්වල් බළලා|செர்வல் பூனை|wild|medium|spotted|active|fast|jump|default|6",
            "caracal|wild|high|Caracal|කැරකල් බළලා|காரக்கல் பூனை|wild|medium|short|active|brave|jump|default|6",
            "ocelot|wild|standard|Ocelot|ඔසෙලොට් බළලා|ஒசெலாட் பூனை|jungle|medium|spotted|active|sneaky|climb|default|7",
            "margay|wild|standard|Margay Cat|මාගේ බළලා|மார்கே பூனை|jungle|small|spotted|active|sneaky|climb|default|3",
            "jaguarundi|wild|standard|Jaguarundi|ජගුවරුන්ඩි|ஜாகுவாруண்டி|jungle|medium|short|active|sneaky|hunt|default|7",
            "pallas_cat|wild|low|Pallas's Cat|පල්ලාස් බළලා|பல்லாஸ் பூனை|wild|small|fluffy|quiet|calm|sleep|default|8",
            "sand_cat|wild|high|Sand Cat|වැලි බළලා|மணல் பூனை|wild|small|short|active|curious|hunt|default|9",
            "fishing_cat|wild|roar|Fishing Cat|හඳුන් දිවියා|மீன்பிடி பூனை|jungle|medium|spotted|active|strong|swim|default|1",
            "wildcat|wild|standard|Wildcat|කැලෑ බළලා|காட்டுப்பூனை|wild|medium|striped|active|brave|hunt|default|7",

            // Fantasy/Fun Cats (81 - 100)
            "space_cat|fantasy|high|Space Cat|අභ්‍යවකාශ පූසා|விண்வெளி பூனை|space|medium|short|curious|active|fly|space|0",
            "ninja_cat|fantasy|standard|Ninja Cat|නින්ජා පූසා|நிஞ்ஜா பூனை|japan|medium|short|quiet|sneaky|jump|ninja|1",
            "robot_cat|fantasy|standard|Robot Cat|රොබෝ පූසා|ரோபோ பூனை|unknown|medium|metallic|smart|active|compute|robot|2",
            "chef_cat|fantasy|standard|Chef Cat|චෙෆ් පූසා|சமையல் கலைஞர் பூனை|france|medium|short|friendly|funny|bake|chef|3",
            "mermaid_cat|fantasy|high|Mermaid Cat|මර්මේඩ් පූසා|கடல் கன்னி பூனை|ocean|medium|fluffy|magical|friendly|swim|mermaid|4",
            "wizard_cat|fantasy|high|Wizard Cat|මායාකාරී පූසා|மந்திரவாதி பூனை|dreamland|medium|fluffy|magical|smart|explore|wizard|5",
            "pirate_cat|fantasy|standard|Pirate Cat|කොල්ලකරු පූසා|கடற்கொள்ளையர் பூனை|ocean|medium|short|brave|funny|explore|default|6",
            "detective_cat|fantasy|standard|Detective Cat|රහස් පරීක්ෂක පූසා|துப்பறியும் பூனை|uk|medium|short|smart|curious|explore|default|7",
            "superhero_cat|fantasy|high|Superhero Cat|සුපිරි වීර පූසා|சூப்பர் ஹீரோ பூனை|dreamland|medium|short|brave|strong|fly|default|8",
            "rainbow_cat|fantasy|high|Rainbow Cat|දේදුනු පූසා|வானவில் பூனை|dreamland|medium|rainbow|magical|friendly|fly|default|7",
            "fairy_cat|fantasy|high|Fairy Cat|සුරංගනා පූසා|தேவதை பூனை|dreamland|small|fluffy|magical|gentle|fly|default|8",
            "disco_cat|fantasy|standard|Disco Cat|ඩිස්කෝ පූසා|டிஸ்கோ பூனை|unknown|medium|short|active|funny|play|default|9",
            "gamer_cat|fantasy|standard|Gamer Cat|ගේමර් පූසා|கேமர் பூனை|unknown|medium|short|active|smart|compute|default|9",
            "candy_cat|fantasy|high|Candy Cat|කැන්ඩි පූසා|மிட்டாய் பூனை|dreamland|small|short|sweet|friendly|play|default|7",
            "sleepy_cat|fantasy|low|Sleepy Cat|නිදිමත පූසා|தூங்கும் பூனை|dreamland|medium|fluffy|calm|quiet|sleep|default|5",
            "ninja_white|fantasy|standard|White Ninja Cat|සුදු නින්ජා පූසා|வெள்ளை நிஞ்ஜா பூனை|japan|medium|short|quiet|sneaky|jump|ninja|1",
            "astro_kitten|fantasy|high|Astronaut Kitten|අභ්‍යවකාශ පැටියා|விண்வெளி பூனைக்குட்டி|space|small|short|curious|playful|fly|space|0",
            "fire_cat|fantasy|high|Fire Cat|ගිනි පූසා|நெருப்பு பூனை|dreamland|medium|striped|active|brave|jump|default|9",
            "ice_cat|fantasy|standard|Ice Cat|අයිස් පූසා|பனி பூனை|dreamland|medium|fluffy|calm|quiet|sleep|default|8",
            "golden_lucky|fantasy|high|Golden Lucky Cat|රන් වාසනාවන්ත පූසා|தங்க அதிர்ஷ்ட பூனை|japan|medium|metallic|friendly|magical|explore|default|9"
        ];

        // Global parsed database
        let catsData = [];

        // Parsing system: converts compact strings into full objects
        function parseCatDatabase() {
            catsData = rawCatsList.map(str => {
                const parts = str.split('|');
                const id = parts[0];
                const category = parts[1];
                const soundType = parts[2];
                const nameEn = parts[3];
                const nameSi = parts[4];
                const nameTa = parts[5];
                const originKey = parts[6];
                const sizeKey = parts[7];
                const furKey = parts[8];
                const char1Key = parts[9];
                const char2Key = parts[10];
                const actionKey = parts[11];
                const factKey = parts[12];
                const imageIdx = parseInt(parts[13]);

                // Assign image from specific pools
                let imgUrl = "";
                if (category === 'wild') {
                    imgUrl = imgPoolWild[imageIdx % imgPoolWild.length];
                } else if (category === 'fantasy') {
                    imgUrl = imgPoolFantasy[imageIdx % imgPoolFantasy.length];
                } else {
                    imgUrl = imgPoolDomestic[imageIdx % imgPoolDomestic.length];
                }

                // Add exceptions for top specific images
                if (id === 'persian') imgUrl = "https://images.unsplash.com/photo-1614035030394-b6e5b01e0737?auto=format&fit=crop&w=600&q=80";
                if (id === 'siamese') imgUrl = "https://images.unsplash.com/photo-1555685812-4b943f1cb0eb?auto=format&fit=crop&w=600&q=80";
                if (id === 'maine_coon') imgUrl = "https://images.unsplash.com/photo-1589952283406-b53a7d1347e8?auto=format&fit=crop&w=600&q=80";
                if (id === 'bengal') imgUrl = "https://images.unsplash.com/photo-1577023311546-cdc07a8454c9?auto=format&fit=crop&w=600&q=80";
                if (id === 'sphynx') imgUrl = "https://images.unsplash.com/photo-1520315342629-6ea920342047?auto=format&fit=crop&w=600&q=80";
                if (id === 'scottish') imgUrl = "https://images.unsplash.com/photo-1573865526739-10659fec78a5?auto=format&fit=crop&w=600&q=80";
                if (id === 'lion') imgUrl = "https://images.unsplash.com/photo-1546182990-dffeafbe841d?auto=format&fit=crop&w=600&q=80";
                if (id === 'tiger') imgUrl = "https://images.unsplash.com/photo-1507666405895-422edf31e40d?auto=format&fit=crop&w=600&q=80";
                if (id === 'cheetah') imgUrl = "https://images.unsplash.com/photo-1534447677768-be436bb09401?auto=format&fit=crop&w=600&q=80";

                return {
                    id,
                    category,
                    soundType,
                    names: { en: nameEn, si: nameSi, ta: nameTa },
                    originKey,
                    sizeKey,
                    furKey,
                    charsKeys: [char1Key, char2Key],
                    actionKey,
                    factKey,
                    image: imgUrl
                };
            });
        }

        // Translation Sentence Builder (Template Engine)
        function generateDescription(cat, lang) {
            const name = cat.names[lang];
            const size = dictSizes[cat.sizeKey][lang];
            const origin = dictOrigins[cat.originKey][lang];
            const char1 = dictChars[cat.charsKeys[0]][lang];
            const char2 = dictChars[cat.charsKeys[1]][lang];
            const fur = dictFurs[cat.furKey][lang];
            const action = dictActions[cat.actionKey][lang];

            if (lang === 'en') {
                if (cat.category === 'wild') {
                    return `The ${name} is a ${size} wild cat found in ${origin}. They are known for being very ${char1} and ${char2}, with a beautiful ${fur} coat. They love to ${action}!`;
                } else if (cat.category === 'fantasy') {
                    return `The ${name} is a ${size} magical cat from ${origin}. They are extremely ${char1} and ${char2}, having a unique ${fur} style! They love to ${action}.`;
                } else {
                    return `The ${name} is a ${size} domestic cat originally from ${origin}. They are famous for being ${char1} and ${char2}, with a gorgeous ${fur} coat. They love to ${action}!`;
                }
            } else if (lang === 'si') {
                if (cat.category === 'wild') {
                    return `${name} යනු ${origin} ආශ්‍රිතව වෙසෙන ${size} ප්‍රමාණයේ කැලෑ බළලෙකි. මොවුන් ඉතා ${char1} මෙන්ම ${char2} සතෙකු වන අතර ${fur} සිරුරක් පිහිටා තිබේ. ඔවුන් ${action} කිරීමට වඩාත් ප්‍රිය කරති.`;
                } else if (cat.category === 'fantasy') {
                    return `${name} යනු ${origin} දේශයෙන් පැමිණි ${size} ප්‍රමාණයේ අපූරු මායාකාරී පූසෙකි. මොවුන් ඉතා ${char1} මෙන්ම ${char2} වන අතර විශේෂ ${fur} පෙනුමක් ඇත! ඔවුන් ${action} කිරීමට කැමතියි.`;
                } else {
                    return `${name} යනු ${origin} පැවත එන ${size} ප්‍රමාණයේ සුරතල් බළලෙකි. මොවුන් ඉතා ${char1} සහ ${char2} වීම නිසා ප්‍රසිද්ධ වන අතර, ${fur} ලොම් සහිත වේ. ඔවුන් ${action} කිරීමට බෙහෙවින් ප්‍රිය කරති.`;
                }
            } else if (lang === 'ta') {
                if (cat.category === 'wild') {
                    return `${name} என்பது ${origin} பகுதிகளில் காணப்படும் ஒரு ${size} காட்டு பூனை இனமாகும். இவை மிகவும் ${char1} மற்றும் ${char2} குணத்திற்குப் பெயர் பெற்றவை, அத்துடன் அழகான ${fur} உடலமைப்பைக் கொண்டவை. இவை ${action} செய்ய மிகவும் விரும்புகின்றன.`;
                } else if (cat.category === 'fantasy') {
                    return `${name} என்பது ${origin} இல் இருந்து வந்த ஒரு ${size} மாயாஜால பூனையாகும். இவை மிகவும் ${char1} மற்றும் ${char2} குணமும், தனித்துவமான ${fur} தோற்றமும் கொண்டவை! இவை ${action} செய்ய விரும்புகின்றன.`;
                } else {
                    return `${name} என்பது ${origin} இல் இருந்து உருவான ஒரு ${size} வீட்டு பூனை இனமாகும். இவை மிகவும் ${char1} மற்றும் ${char2} குணத்திற்குப் பெயர் பெற்றவை, அத்துடன் அழகான ${fur} முடிகளையும் கொண்டவை. இவை ${action} செய்ய மிகவும் விரும்புகின்றன.`;
                }
            }
            return "";
        }

        // Quiz Questions Database (Translated)
        const quizDatabase = {
            en: [
                {
                    question: "Which cat is known as the 'Gentle Giant' and loves playing in water?",
                    options: ["Persian Cat", "Maine Coon", "Siamese Cat", "Cheetah"],
                    correct: 1
                },
                {
                    question: "Lions live in groups called what?",
                    options: ["Herds", "Packs", "Prides", "Flocks"],
                    correct: 2
                },
                {
                    question: "Which cat is completely hairless and feels warm like a peach?",
                    options: ["Sphynx Cat", "Bengal Cat", "Scottish Fold", "Siamese Cat"],
                    correct: 0
                },
                {
                    question: "What is the fastest wild cat on land?",
                    options: ["Lion", "Bengal Cat", "Persian Cat", "Cheetah"],
                    correct: 3
                },
                {
                    question: "Which fantasy cat loves to fly high in the clouds and comes from Dreamland?",
                    options: ["Mermaid Cat", "Rainbow Cat", "Robot Cat", "Ninja Cat"],
                    correct: 1
                }
            ],
            si: [
                {
                    question: "ජලයේ සෙල්ලම් කිරීමට ප්‍රිය කරන 'මෘදු යෝධයා' ලෙස හඳුන්වන පූසා කවුද?",
                    options: ["පර්සියානු බළලා", "මේන් කූන් බළලා", "සියම් බළලා", "චීටා"],
                    correct: 1
                },
                {
                    question: "සිංහයන් රංචු වශයෙන් ජීවත් වන කණ්ඩායම්වලට කියන්නේ කුමක්ද?",
                    options: ["රංචු (Herds)", "පැක් (Packs)", "ප්‍රයිඩ්ස් (Prides)", "රෑන් (Flocks)"],
                    correct: 2
                },
                {
                    question: "ලොම් සම්පූර්ණයෙන්ම නොමැති, ඇල්ලූ විට උණුසුම්ව දැනෙන පූසා කවුද?",
                    options: ["ස්පින්ක්ස් බළලා", "බෙංගාලි බළලා", "ස්කොටිෂ් ෆෝල්ඩ් බළලා", "සියම් බළලා"],
                    correct: 0
                },
                {
                    question: "ගොඩබිම වෙසෙන වේගවත්ම කැලෑ බළලා කවුද?",
                    options: ["සිංහයා", "බෙංගාලි බළලා", "පර්සියානු බළලා", "චීටා"],
                    correct: 3
                },
                {
                    question: "සිහින ලෝකයෙන් පැමිණි, වලාකුළු අතර පියාසර කිරීමට කැමති දේදුනු පූසා කවුද?",
                    options: ["මර්මේඩ් පූසා", "දේදුනු පූසා", "රොබෝ පූසා", "නින්ජා පූසා"],
                    correct: 1
                }
            ],
            ta: [
                {
                    question: "நீரில் விளையாட விரும்பும் மற்றும் 'அன்பான ராட்சதர்' என்று அழைக்கப்படும் பூனை எது?",
                    options: ["பெர்சியன் பூனை", "மைனே கூன் பூனை", "சியாமிய பூனை", "சிறுத்தை"],
                    correct: 1
                },
                {
                    question: "சிங்கங்களின் கூட்டத்திற்கு என்ன பெயர்?",
                    options: ["மந்தை (Herds)", "கூட்டம் (Packs)", "பிரைடு (Prides)", "குழு (Flocks)"],
                    correct: 2
                },
                {
                    question: "உடலில் முடி இல்லாமல், தொடுவதற்கு மிதமான சூடாக இருக்கும் பூனை எது?",
                    options: ["ஸ்பின்க்ஸ் பூனை", "வங்காள பூனை", "ஸகாட்டிஷ் மடிப்பு", "சியாமிய பூனை"],
                    correct: 0
                },
                {
                    question: "நிலத்தில் மிக வேகமாக ஓடக்கூடிய காட்டு பூனை எது?",
                    options: ["சிங்கம்", "வங்காள பூனை", "பெர்சியன் பூனை", "சிறுத்தை"],
                    correct: 3
                },
                {
                    question: "கனவுலகில் இருந்து வந்த, மேகங்களில் பறக்க விரும்பும் வானவில் பூனை எது?",
                    options: ["கடல் கன்னி பூனை", "வானவில் பூனை", "ரோபோ பூனை", "நிஞ்ஜா பூனை"],
                    correct: 1
                }
            ]
        };

        // Pagination variables
        let currentCategory = 'all';
        let searchQuery = '';
        let catsVisibleCount = 12; // Load 12 cats initially
        const incrementLoadCount = 12;

        // Initialize App
        function initApp() {
            parseCatDatabase();
            createBubbles();
            switchLanguage('en');
            initQuiz();
        }

        // Animated Background Bubbles
        function createBubbles() {
            const ambientBg = document.getElementById('ambientBg');
            for (let i = 0; i < 15; i++) {
                const bubble = document.createElement('div');
                bubble.className = 'bubble';
                const size = Math.random() * 80 + 30;
                bubble.style.width = `${size}px`;
                bubble.style.height = `${size}px`;
                bubble.style.left = `${Math.random() * 100}vw`;
                bubble.style.bottom = `-100px`;
                bubble.style.animationDelay = `${Math.random() * 10}s`;
                bubble.style.animationDuration = `${Math.random() * 15 + 10}s`;
                ambientBg.appendChild(bubble);
            }
        }

        // Switch Language
        function switchLanguage(lang) {
            currentLang = lang;
            
            document.querySelectorAll('.lang-btn').forEach(btn => btn.classList.remove('active'));
            if (lang === 'en') document.querySelectorAll('.lang-btn')[0].classList.add('active');
            if (lang === 'si') document.querySelectorAll('.lang-btn')[1].classList.add('active');
            if (lang === 'ta') document.querySelectorAll('.lang-btn')[2].classList.add('active');

            document.getElementById('ui-title').innerText = uiTranslations[lang].title;
            document.getElementById('ui-subtitle').innerText = uiTranslations[lang].subtitle;
            document.getElementById('searchBar').placeholder = uiTranslations[lang].searchPlaceholder;
            document.getElementById('ui-all').innerText = uiTranslations[lang].all;
            document.getElementById('ui-fluffy').innerText = uiTranslations[lang].fluffy;
            document.getElementById('ui-playful').innerText = uiTranslations[lang].playful;
            document.getElementById('ui-wild').innerText = uiTranslations[lang].wild;
            document.getElementById('ui-fantasy').innerText = uiTranslations[lang].fantasy;
            document.getElementById('ui-quiz-title').innerText = uiTranslations[lang].quizTitle;
            document.getElementById('ui-quiz-desc').innerText = uiTranslations[lang].quizDesc;
            document.getElementById('ui-score-label').innerText = uiTranslations[lang].scoreLabel;
            document.getElementById('ui-success-title').innerText = uiTranslations[lang].successTitle;
            document.getElementById('ui-success-desc').innerText = uiTranslations[lang].successDesc;
            document.getElementById('ui-restart-btn').innerText = uiTranslations[lang].restartBtn;
            document.getElementById('noResults').innerText = uiTranslations[lang].noResults;
            document.getElementById('ui-loadmore').innerText = uiTranslations[lang].loadMore;
            document.getElementById('chatBubble').innerText = uiTranslations[lang].helperIntro;

            renderCatGrid();
            renderQuestion();
        }

        // Render Cat Grid Cards with Pagination
        function renderCatGrid() {
            const grid = document.getElementById('catGrid');
            grid.innerHTML = '';
            
            // Filter set
            const filteredCats = catsData.filter(cat => {
                const name = cat.names[currentLang];
                const desc = generateDescription(cat, currentLang);
                
                const matchesSearch = name.toLowerCase().includes(searchQuery.toLowerCase()) || 
                                     desc.toLowerCase().includes(searchQuery.toLowerCase());
                                     
                let matchesCategory = false;
                if (currentCategory === 'all') {
                    matchesCategory = true;
                } else if (currentCategory === 'fluffy') {
                    matchesCategory = (cat.category === 'fluffy');
                } else if (currentCategory === 'playful') {
                    matchesCategory = (cat.category === 'playful');
                } else if (currentCategory === 'wild') {
                    matchesCategory = (cat.category === 'wild');
                } else if (currentCategory === 'fantasy') {
                    matchesCategory = (cat.category === 'fantasy');
                }
                
                return matchesSearch && matchesCategory;
            });

            const totalFilteredCount = filteredCats.length;
            const displaySet = filteredCats.slice(0, catsVisibleCount);

            displaySet.forEach(cat => {
                const name = cat.names[currentLang];
                const desc = generateDescription(cat, currentLang);
                const funFact = dictFunFacts[cat.factKey][currentLang];
                const sizeLabel = dictSizes[cat.sizeKey][currentLang];
                const lifespan = cat.category === 'wild' ? "10-15 years" : "12-18 years";

                // Generate personality badges
                let tagsHtml = '';
                cat.charsKeys.forEach((charKey, idx) => {
                    const charTranslated = dictChars[charKey][currentLang];
                    tagsHtml += `<span class="personality-tag tag-${idx}">${charTranslated}</span>`;
                });

                const card = document.createElement('div');
                card.className = 'cat-card';
                card.id = `card-${cat.id}`;
                
                card.innerHTML = `
                    <div class="ear-inner-l"></div>
                    <div class="ear-inner-r"></div>

                    <div class="cat-img-wrapper">
                        <img src="${cat.image}" alt="${name}" onerror="this.src='https://images.unsplash.com/photo-1514888286974-6c03e2ca1dba?auto=format&fit=crop&w=600&q=80'">
                        <span class="category-badge">
                            ${cat.category === 'fluffy' ? '☁️ Fluffy' : cat.category === 'playful' ? '⚡ Playful' : cat.category === 'wild' ? '🦁 Wild' : '✨ Fantasy'}
                        </span>
                    </div>
                    <div class="cat-info">
                        <h3 class="cat-name">${name}</h3>
                        <p class="cat-desc">${desc}</p>
                        <div class="tag-container">
                            ${tagsHtml}
                        </div>
                        <div class="fact-bubble">
                            ${funFact}
                        </div>
                        <div class="card-actions">
                            <button class="card-btn btn-sound" onclick="playSound('${cat.soundType}')">
                                ${uiTranslations[currentLang].btnHear}
                            </button>
                            <button class="card-btn btn-stats" onclick="toggleStats('${cat.id}', true)">
                                ${uiTranslations[currentLang].btnStats}
                            </button>
                        </div>
                    </div>

                    <!-- Stats drawer sliding overlay -->
                    <div class="stats-drawer" id="stats-${cat.id}">
                        <div class="stats-header">
                            <h3>${name}</h3>
                            <button class="close-stats" onclick="toggleStats('${cat.id}', false)">×</button>
                        </div>
                        <div class="stat-row">
                            <span class="stat-label">${uiTranslations[currentLang].statsSize}:</span>
                            <span class="stat-val">${sizeLabel}</span>
                        </div>
                        <div class="stat-row">
                            <span class="stat-label">${uiTranslations[currentLang].statsLife}:</span>
                            <span class="stat-val">${lifespan}</span>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            });

            // Update Counter Badge
            const counterText = uiTranslations[currentLang].showingLabel
                .replace('{show}', displaySet.length)
                .replace('{total}', totalFilteredCount);
            document.getElementById('counterBadge').innerText = counterText;

            // Load More button visibility
            const paginationContainer = document.getElementById('paginationContainer');
            if (catsVisibleCount >= totalFilteredCount) {
                paginationContainer.style.display = 'none';
            } else {
                paginationContainer.style.display = 'block';
            }

            // Handle Empty Results
            const noResults = document.getElementById('noResults');
            if (totalFilteredCount === 0) {
                noResults.style.display = 'block';
                paginationContainer.style.display = 'none';
            } else {
                noResults.style.display = 'none';
            }
        }

        // Load More Cats
        function loadMoreCats() {
            catsVisibleCount += incrementLoadCount;
            renderCatGrid();
        }

        // Toggle Stats Drawer
        function toggleStats(catId, isOpen) {
            const drawer = document.getElementById(`stats-${catId}`);
            if (isOpen) {
                drawer.classList.add('open');
            } else {
                drawer.classList.remove('open');
            }
        }

        // Filter Cats by Category
        function filterCategory(category) {
            currentCategory = category;
            catsVisibleCount = 12; // Reset pagination count on filter change
            
            document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
            document.getElementById(`btn-${category}`).classList.add('active');

            renderCatGrid();
        }

        // Filter Cats by Search
        function filterCats() {
            searchQuery = document.getElementById('searchBar').value;
            catsVisibleCount = 12; // Reset pagination count on search change
            renderCatGrid();
        }

        // Programmatic Web Audio Synthesizer (Realistic sounds generated on-the-fly)
        function playSound(type) {
            const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            if (audioCtx.state === 'suspended') audioCtx.resume();

            const osc = audioCtx.createOscillator();
            const gainNode = audioCtx.createGain();
            osc.connect(gainNode);
            gainNode.connect(audioCtx.destination);
            
            const now = audioCtx.currentTime;
            
            if (type === 'high') { // Kitten high pitch sweep meow
                osc.type = 'triangle';
                osc.frequency.setValueAtTime(550, now);
                osc.frequency.exponentialRampToValueAtTime(1050, now + 0.15);
                osc.frequency.exponentialRampToValueAtTime(750, now + 0.38);
                
                gainNode.gain.setValueAtTime(0, now);
                gainNode.gain.linearRampToValueAtTime(0.35, now + 0.05);
                gainNode.gain.exponentialRampToValueAtTime(0.01, now + 0.38);
                osc.start(now);
                osc.stop(now + 0.4);
                
            } else if (type === 'low') { // Maine Coon deep meow
                osc.type = 'sawtooth';
                const filter = audioCtx.createBiquadFilter();
                filter.type = 'lowpass';
                filter.frequency.setValueAtTime(650, now);
                
                osc.disconnect(gainNode);
                osc.connect(filter);
                filter.connect(gainNode);
                
                osc.frequency.setValueAtTime(280, now);
                osc.frequency.exponentialRampToValueAtTime(420, now + 0.22);
                osc.frequency.exponentialRampToValueAtTime(320, now + 0.6);
                
                gainNode.gain.setValueAtTime(0, now);
                gainNode.gain.linearRampToValueAtTime(0.4, now + 0.08);
                gainNode.gain.exponentialRampToValueAtTime(0.01, now + 0.6);
                osc.start(now);
                osc.stop(now + 0.6);
                
            } else if (type === 'purr') { // Rapid sine-wave gain modulation (Purring)
                osc.type = 'sine';
                osc.frequency.setValueAtTime(35, now);
                
                const mod = audioCtx.createOscillator();
                const modGain = audioCtx.createGain();
                mod.frequency.value = 24;
                modGain.gain.value = 0.55;
                
                mod.connect(modGain);
                modGain.connect(gainNode.gain);
                
                gainNode.gain.setValueAtTime(0.2, now);
                gainNode.gain.linearRampToValueAtTime(0.2, now + 1.4);
                gainNode.gain.exponentialRampToValueAtTime(0.01, now + 1.5);
                
                mod.start(now);
                osc.start(now);
                osc.stop(now + 1.5);
                mod.stop(now + 1.5);
                
            } else if (type === 'roar') { // Wild Cat Roar (Low frequency rumble + Bandpass-filtered random noise)
                // Low Rumble
                const rumble = audioCtx.createOscillator();
                rumble.type = 'sawtooth';
                rumble.frequency.setValueAtTime(65, now);
                rumble.frequency.linearRampToValueAtTime(35, now + 1.2);
                
                const rumbleFilter = audioCtx.createBiquadFilter();
                rumbleFilter.type = 'lowpass';
                rumbleFilter.frequency.value = 90;
                
                const rumbleGain = audioCtx.createGain();
                rumbleGain.gain.setValueAtTime(0.7, now);
                rumbleGain.gain.exponentialRampToValueAtTime(0.01, now + 1.3);
                
                rumble.connect(rumbleFilter);
                rumbleFilter.connect(rumbleGain);
                rumbleGain.connect(audioCtx.destination);
                
                // Noise element
                const bufferSize = audioCtx.sampleRate * 1.5;
                const buffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate);
                const data = buffer.getChannelData(0);
                for (let i = 0; i < bufferSize; i++) {
                    data[i] = Math.random() * 2 - 1;
                }
                
                const noiseNode = audioCtx.createBufferSource();
                noiseNode.buffer = buffer;
                
                const noiseFilter = audioCtx.createBiquadFilter();
                noiseFilter.type = 'bandpass';
                noiseFilter.frequency.setValueAtTime(140, now);
                noiseFilter.frequency.exponentialRampToValueAtTime(55, now + 0.9);
                noiseFilter.Q.value = 2.5;
                
                noiseNode.connect(noiseFilter);
                noiseFilter.connect(gainNode);
                
                gainNode.gain.setValueAtTime(0.85, now);
                gainNode.gain.linearRampToValueAtTime(0.85, now + 0.35);
                gainNode.gain.exponentialRampToValueAtTime(0.01, now + 1.4);
                
                rumble.start(now);
                noiseNode.start(now);
                rumble.stop(now + 1.4);
                noiseNode.stop(now + 1.4);
                
            } else { // Standard Meow (Classic)
                osc.type = 'triangle';
                osc.frequency.setValueAtTime(420, now);
                osc.frequency.exponentialRampToValueAtTime(780, now + 0.16);
                osc.frequency.exponentialRampToValueAtTime(520, now + 0.45);
                
                gainNode.gain.setValueAtTime(0, now);
                gainNode.gain.linearRampToValueAtTime(0.4, now + 0.05);
                gainNode.gain.exponentialRampToValueAtTime(0.01, now + 0.45);
                osc.start(now);
                osc.stop(now + 0.45);
            }
        }

        // Quiz Engine State
        let currentQuizIndex = 0;
        let score = 0;
        let answered = false;

        function initQuiz() {
            currentQuizIndex = 0;
            score = 0;
            answered = false;
            document.getElementById('score').innerText = '0';
            document.getElementById('quiz-play-
