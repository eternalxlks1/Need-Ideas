# Idea #2
this idea is for something but i think its a idea generator!

## this is for lower ranks
like ultra pro, or noober pro.

## Code
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Ideas Generator</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            padding: 40px;
            max-width: 700px;
            width: 100%;
        }

        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 10px;
            font-size: 2.5em;
        }

        .subtitle {
            text-align: center;
            color: #666;
            margin-bottom: 30px;
            font-size: 1.1em;
        }

        .controls {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        select, button {
            flex: 1;
            min-width: 150px;
            padding: 12px 20px;
            border: none;
            border-radius: 10px;
            font-size: 1em;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
        }

        select {
            background: #f0f0f0;
            color: #333;
            border: 2px solid #667eea;
        }

        select:hover {
            background: #e0e0e0;
        }

        .btn-generate {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .btn-generate:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.4);
        }

        .btn-clear {
            background: #ff6b6b;
            color: white;
        }

        .btn-clear:hover {
            background: #ee5a52;
            transform: translateY(-2px);
        }

        .idea-display {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 15px;
            padding: 30px;
            min-height: 150px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: white;
            text-align: center;
            margin-bottom: 20px;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.2);
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .idea-category {
            font-size: 0.9em;
            opacity: 0.9;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .idea-text {
            font-size: 1.6em;
            font-weight: bold;
            margin-bottom: 15px;
            line-height: 1.4;
        }

        .copy-btn {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 2px solid white;
            padding: 8px 16px;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.9em;
            font-weight: 600;
        }

        .copy-btn:hover {
            background: white;
            color: #667eea;
        }

        .placeholder {
            font-size: 1.2em;
            opacity: 0.7;
        }

        .stats {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 20px;
        }

        .stat-box {
            background: #f5f5f5;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
        }

        .stat-number {
            font-size: 1.8em;
            font-weight: bold;
            color: #667eea;
        }

        .stat-label {
            font-size: 0.9em;
            color: #666;
            margin-top: 5px;
        }

        @media (max-width: 600px) {
            .container {
                padding: 20px;
            }

            h1 {
                font-size: 1.8em;
            }

            .controls {
                flex-direction: column;
            }

            select, button {
                width: 100%;
                min-width: auto;
            }

            .idea-text {
                font-size: 1.3em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>💡 Project Ideas Generator</h1>
        <p class="subtitle">Get inspired with random project ideas</p>

        <div class="controls">
            <select id="categorySelect">
                <option value="">All Categories</option>
                <option value="web">Web Development</option>
                <option value="mobile">Mobile Apps</option>
                <option value="ai">AI & Machine Learning</option>
                <option value="games">Games</option>
                <option value="tools">Tools & Utilities</option>
                <option value="data">Data Science</option>
                <option value="automation">Automation</option>
            </select>
            <button class="btn-generate" onclick="generateIdea()">Generate Idea</button>
            <button class="btn-clear" onclick="clearIdea()">Clear</button>
        </div>

        <div class="idea-display" id="ideaDisplay">
            <p class="placeholder">Click "Generate Idea" to get started! 🚀</p>
        </div>

        <div class="stats">
            <div class="stat-box">
                <div class="stat-number" id="totalIdeas">0</div>
                <div class="stat-label">Ideas Generated</div>
            </div>
            <div class="stat-box">
                <div class="stat-number" id="categoryCount">8</div>
                <div class="stat-label">Categories</div>
            </div>
        </div>
    </div>

    <script>
        const ideas = {
            web: [
                "Build a personal portfolio website with dark mode toggle",
                "Create a collaborative note-taking app with real-time sync",
                "Develop a recipe sharing platform with ingredient search",
                "Build a workout tracker dashboard with progress visualization",
                "Create a movie/book recommendation engine",
                "Develop a weather app with historical data analysis",
                "Build a task management app with Kanban board",
                "Create a URL shortener with analytics",
                "Develop a calendar app with event reminders",
                "Build a music streaming metadata explorer"
            ],
            mobile: [
                "Create a habit tracking app with streak counter",
                "Build a meditation app with guided sessions",
                "Develop a local event discovery app",
                "Create a language learning app with flashcards",
                "Build a fitness challenge app for friend groups",
                "Develop a parking spot finder app",
                "Create a book club discussion app",
                "Build a meal planning and grocery list app",
                "Develop a pet care reminder app",
                "Create a budget tracking app with spending insights"
            ],
            ai: [
                "Train a model to detect sentiment in movie reviews",
                "Build a chatbot for customer support automation",
                "Create an image classification system for plant diseases",
                "Develop a recommendation engine for similar products",
                "Build a text summarization tool",
                "Create a spam email detector",
                "Develop a predictive model for stock prices",
                "Build an AI writing assistant for better emails",
                "Create a facial recognition attendance system",
                "Develop a music genre classifier"
            ],
            games: [
                "Create a 2D platformer game with Unity",
                "Build a puzzle game similar to Tetris or Match-3",
                "Develop a text-based adventure game",
                "Create a strategy card game",
                "Build a multiplayer quiz game",
                "Develop a dungeon crawler RPG",
                "Create a rhythm/music-based game",
                "Build a retro snake/pac-man style game",
                "Develop a turn-based strategy game",
                "Create a physics-based puzzle game"
            ],
            tools: [
                "Build a JSON formatter and validator",
                "Create a color palette generator",
                "Develop a code snippet manager with search",
                "Build a markdown to HTML converter",
                "Create a screen time tracker and limiter",
                "Develop a backup automation tool",
                "Build a file batch renamer",
                "Create a password strength analyzer",
                "Develop a to-do CLI tool",
                "Build a changelog generator from git commits"
            ],
            data: [
                "Analyze COVID-19 vaccination trends across regions",
                "Create a stock market analysis dashboard",
                "Build a housing price prediction model",
                "Analyze social media sentiment during major events",
                "Create a weather pattern analyzer",
                "Build a customer churn prediction model",
                "Analyze crime statistics by neighborhood",
                "Create a sports performance analytics dashboard",
                "Build an air quality predictor",
                "Analyze GitHub trending repositories"
            ],
            automation: [
                "Automate daily reports generation from data",
                "Create a file organization bot",
                "Build an automated backup system",
                "Automate social media post scheduling",
                "Create a web scraper for price comparison",
                "Build an email filter and auto-responder",
                "Automate database cleanup routines",
                "Create a log analyzer with alerts",
                "Build an automated testing pipeline",
                "Create a bill payment reminder bot"
            ]
        };

        let generatedCount = 0;
        let currentIdea = null;

        function generateIdea() {
            const category = document.getElementById('categorySelect').value;
            let availableIdeas = [];

            if (category) {
                availableIdeas = ideas[category];
            } else {
                availableIdeas = Object.values(ideas).flat();
            }

            if (availableIdeas.length === 0) return;

            const randomIndex = Math.floor(Math.random() * availableIdeas.length);
            currentIdea = availableIdeas[randomIndex];
            const categoryName = category || 'random';

            const ideaDisplay = document.getElementById('ideaDisplay');
            ideaDisplay.innerHTML = `
                <div class="idea-category">${categoryName.toUpperCase()}</div>
                <div class="idea-text">${currentIdea}</div>
                <button class="copy-btn" onclick="copyToClipboard()">📋 Copy Idea</button>
            `;

            generatedCount++;
            document.getElementById('totalIdeas').textContent = generatedCount;
        }

        function clearIdea() {
            document.getElementById('ideaDisplay').innerHTML = '<p class="placeholder">Click "Generate Idea" to get started! 🚀</p>';
            currentIdea = null;
        }

        function copyToClipboard() {
            if (currentIdea) {
                navigator.clipboard.writeText(currentIdea).then(() => {
                    const btn = event.target;
                    btn.textContent = '✅ Copied!';
                    setTimeout(() => {
                        btn.textContent = '📋 Copy Idea';
                    }, 2000);
                });
            }
        }
    </script>
</body>
</html>
