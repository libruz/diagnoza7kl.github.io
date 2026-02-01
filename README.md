<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DIAGNOZA Z J. ANGIELSKIEGO KLASA 7</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-green: #2e7d32;
            --light-green: #4caf50;
            --lighter-green: #81c784;
            --background-green: #e8f5e9;
            --dark-green: #1b5e20;
            --yellow: #ffeb3b;
            --gray: #bdbdbd;
            --dark-gray: #757575;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            background-color: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }
        
        .header {
            background: linear-gradient(135deg, var(--primary-green), var(--dark-green));
            color: white;
            padding: 25px;
            text-align: center;
            border-bottom: 5px solid var(--light-green);
        }
        
        .header h1 {
            font-size: 28px;
            margin-bottom: 10px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }
        
        .header .subtitle {
            font-size: 18px;
            opacity: 0.9;
        }
        
        .test-content {
            padding: 30px;
            min-height: 500px;
        }
        
        .task-section {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .task-section.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .task-title {
            color: var(--primary-green);
            border-bottom: 2px solid var(--lighter-green);
            padding-bottom: 10px;
            margin-bottom: 25px;
            font-size: 22px;
        }
        
        .question {
            margin-bottom: 20px;
            padding: 15px;
            background-color: var(--background-green);
            border-radius: 10px;
            border-left: 4px solid var(--light-green);
        }
        
        .question p {
            margin-bottom: 10px;
            font-weight: 600;
            color: var(--dark-green);
        }
        
        input[type="text"], select, textarea {
            padding: 10px 15px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            width: 100%;
            transition: border-color 0.3s;
            resize: vertical;
        }
        
        input[type="text"]:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--light-green);
        }
        
        .audio-player {
            background-color: #f0f7f0;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border: 2px solid var(--lighter-green);
        }
        
        .audio-player button {
            background-color: var(--primary-green);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: background-color 0.3s;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .audio-player button:hover {
            background-color: var(--dark-green);
        }
        
        .audio-player button:disabled {
            background-color: var(--gray);
            cursor: not-allowed;
        }
        
        .audio-counter {
            font-weight: bold;
            color: var(--primary-green);
            background-color: white;
            padding: 5px 15px;
            border-radius: 20px;
            border: 2px solid var(--light-green);
        }
        
        .radio-group {
            display: flex;
            gap: 20px;
            margin-top: 10px;
        }
        
        .radio-option {
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .radio-option input {
            width: auto;
        }
        
        .table-container {
            overflow-x: auto;
            margin-bottom: 20px;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: left;
        }
        
        th {
            background-color: var(--background-green);
            color: var(--dark-green);
            font-weight: 600;
        }
        
        .navigation {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
            padding-top: 20px;
            border-top: 2px solid #eee;
        }
        
        .nav-button {
            background-color: var(--light-green);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        .nav-button:hover {
            background-color: var(--primary-green);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(46, 125, 50, 0.3);
        }
        
        .nav-button:disabled {
            background-color: var(--gray);
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }
        
        .progress-bar {
            display: flex;
            justify-content: center;
            gap: 8px;
            margin-top: 20px;
            flex-wrap: wrap;
            padding: 20px;
            background-color: var(--background-green);
        }
        
        .progress-dot {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: var(--gray);
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
        }
        
        .progress-dot:hover {
            transform: scale(1.1);
        }
        
        .progress-dot.visited {
            background-color: var(--yellow);
            color: #333;
        }
        
        .progress-dot.completed {
            background-color: var(--light-green);
            color: white;
        }
        
        .progress-dot.active {
            box-shadow: 0 0 0 3px white, 0 0 0 5px var(--light-green);
        }
        
        .progress-dot.current {
            background-color: var(--primary-green);
            color: white;
        }
        
        .progress-dot i {
            font-size: 14px;
        }
        
        .save-button {
            background-color: var(--dark-green);
            margin-left: auto;
        }
        
        .student-info-form {
            max-width: 500px;
            margin: 0 auto;
            padding: 30px;
            background-color: var(--background-green);
            border-radius: 15px;
            text-align: center;
        }
        
        .student-info-form h2 {
            color: var(--primary-green);
            margin-bottom: 20px;
        }
        
        .student-info-form input {
            margin-bottom: 20px;
        }
        
        .start-button {
            background-color: var(--primary-green);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            font-size: 18px;
            transition: background-color 0.3s;
            width: 100%;
            margin-top: 10px;
        }
        
        .start-button:hover {
            background-color: var(--dark-green);
        }
        
        .start-button:active {
            transform: scale(0.98);
        }
        
        .completion-message {
            text-align: center;
            padding: 40px;
            background-color: var(--background-green);
            border-radius: 15px;
            margin-top: 20px;
        }
        
        .completion-message h2 {
            color: var(--primary-green);
            margin-bottom: 15px;
        }
        
        .completion-message p {
            margin-bottom: 20px;
            font-size: 18px;
        }
        
        .loading {
            display: none;
            text-align: center;
            padding: 20px;
            color: var(--primary-green);
        }
        
        .loading i {
            font-size: 24px;
            margin-bottom: 10px;
        }
        
        .error-message {
            color: #d32f2f;
            background-color: #ffebee;
            padding: 10px;
            border-radius: 5px;
            margin-top: 10px;
            display: none;
        }
        
        .success-message {
            color: var(--primary-green);
            background-color: #e8f5e9;
            padding: 10px;
            border-radius: 5px;
            margin-top: 10px;
            display: none;
        }
        
        .points-info {
            font-size: 14px;
            color: var(--dark-green);
            font-style: italic;
            margin-top: 5px;
        }
        
        @media (max-width: 768px) {
            .container {
                margin: 10px;
                border-radius: 10px;
            }
            
            .test-content {
                padding: 20px;
            }
            
            .progress-dot {
                width: 35px;
                height: 35px;
                font-size: 14px;
            }
            
            .audio-player {
                flex-direction: column;
                gap: 15px;
                align-items: flex-start;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>DIAGNOZA Z J. ANGIELSKIEGO</h1>
            <div class="subtitle">Klasa 7 - Test diagnozujący (75 punktów)</div>
        </div>
        
        <div class="test-content">
            <!-- Sekcja danych ucznia -->
            <div id="student-section" class="task-section active">
                <div class="student-info-form">
                    <h2><i class="fas fa-user-graduate"></i> Dane ucznia</h2>
                    <p>Przed rozpoczęciem testu podaj swoje imię i nazwisko:</p>
                    <input type="text" id="student-name" placeholder="Imię i nazwisko" required>
                    <button id="start-test" class="start-button" onclick="startTest()">
                        <i class="fas fa-play-circle"></i> Rozpocznij test
                    </button>
                    <div id="student-error" class="error-message">Proszę podać imię i nazwisko</div>
                </div>
            </div>
            
            <!-- Zadanie 1 -->
            <div id="task-1" class="task-section">
                <h2 class="task-title">Zadanie 1 (5 p.)</h2>
                <p>Posłuchaj wypowiedzi (A–E) i dopasuj zdania do osób mówiących (1–5).</p>
                <div class="points-info">5 punktów</div>
                
                <div class="audio-player">
                    <div>
                        <h3><i class="fas fa-volume-up"></i> Nagranie 1</h3>
                        <p>Możesz odsłuchać nagranie maksymalnie 3 razy</p>
                    </div>
                    <div>
                        <button id="play-audio-1" onclick="playAudio(1)">
                            <i class="fas fa-play"></i> Odtwórz nagranie
                        </button>
                        <div class="audio-counter">Pozostało odtworzeń: <span id="audio-counter-1">3</span></div>
                    </div>
                </div>
                
                <div class="question">
                    <p>1. Speaker 1:</p>
                    <select id="q1-1">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. The speaker is talking about plants and animals.</option>
                        <option value="B">B. The speaker is talking about her health problems.</option>
                        <option value="C">C. The speaker is talking about a family celebration.</option>
                        <option value="D">D. The speaker is talking about an environmental problem.</option>
                        <option value="E">E. The speaker is talking about a recipe for delicious pasta.</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>2. Speaker 2:</p>
                    <select id="q1-2">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. The speaker is talking about plants and animals.</option>
                        <option value="B">B. The speaker is talking about her health problems.</option>
                        <option value="C">C. The speaker is talking about a family celebration.</option>
                        <option value="D">D. The speaker is talking about an environmental problem.</option>
                        <option value="E">E. The speaker is talking about a recipe for delicious pasta.</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>3. Speaker 3:</p>
                    <select id="q1-3">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. The speaker is talking about plants and animals.</option>
                        <option value="B">B. The speaker is talking about her health problems.</option>
                        <option value="C">C. The speaker is talking about a family celebration.</option>
                        <option value="D">D. The speaker is talking about an environmental problem.</option>
                        <option value="E">E. The speaker is talking about a recipe for delicious pasta.</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>4. Speaker 4:</p>
                    <select id="q1-4">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. The speaker is talking about plants and animals.</option>
                        <option value="B">B. The speaker is talking about her health problems.</option>
                        <option value="C">C. The speaker is talking about a family celebration.</option>
                        <option value="D">D. The speaker is talking about an environmental problem.</option>
                        <option value="E">E. The speaker is talking about a recipe for delicious pasta.</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>5. Speaker 5:</p>
                    <select id="q1-5">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. The speaker is talking about plants and animals.</option>
                        <option value="B">B. The speaker is talking about her health problems.</option>
                        <option value="C">C. The speaker is talking about a family celebration.</option>
                        <option value="D">D. The speaker is talking about an environmental problem.</option>
                        <option value="E">E. The speaker is talking about a recipe for delicious pasta.</option>
                    </select>
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 2 -->
            <div id="task-2" class="task-section">
                <h2 class="task-title">Zadanie 2 (5 p.)</h2>
                <p>Wysłuchaj nagrania i uzupełnij zdania. W każdą lukę należy wpisać jeden wyraz.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="audio-player">
                    <div>
                        <h3><i class="fas fa-volume-up"></i> Nagranie 2</h3>
                        <p>Możesz odsłuchać nagranie maksymalnie 3 razy</p>
                    </div>
                    <div>
                        <button id="play-audio-2" onclick="playAudio(2)">
                            <i class="fas fa-play"></i> Odtwórz nagranie
                        </button>
                        <div class="audio-counter">Pozostało odtworzeń: <span id="audio-counter-2">3</span></div>
                    </div>
                </div>
                
                <div class="question">
                    <p>1. Eric has got a __________ ankle.</p>
                    <input type="text" id="q2-1" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="question">
                    <p>2. He is probably allergic to some __________.</p>
                    <input type="text" id="q2-2" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="question">
                    <p>3. Lizzy is going to a camp on __________.</p>
                    <input type="text" id="q2-3" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="question">
                    <p>4. Mark has got a __________ nose.</p>
                    <input type="text" id="q2-4" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="question">
                    <p>5. Lizzy is going to stay at the camp for __________ weeks.</p>
                    <input type="text" id="q2-5" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 3 -->
            <div id="task-3" class="task-section">
                <h2 class="task-title">Zadanie 3 (5 p.)</h2>
                <p>Posłuchaj nagrania i określ czy podane zdania są prawdziwe – True (T) czy fałszywe – False (F).</p>
                <div class="points-info">5 punktów</div>
                
                <div class="audio-player">
                    <div>
                        <h3><i class="fas fa-volume-up"></i> Nagranie 3</h3>
                        <p>Możesz odsłuchać nagranie maksymalnie 3 razy</p>
                    </div>
                    <div>
                        <button id="play-audio-3" onclick="playAudio(3)">
                            <i class="fas fa-play"></i> Odtwórz nagranie
                        </button>
                        <div class="audio-counter">Pozostało odtworzeń: <span id="audio-counter-3">3</span></div>
                    </div>
                </div>
                
                <div class="table-container">
                    <table>
                        <tr>
                            <th>Zdanie</th>
                            <th>True (T)</th>
                            <th>False (F)</th>
                        </tr>
                        <tr>
                            <td>1. Waiting in a queue is not for Yasmin.</td>
                            <td class="radio-option"><input type="radio" name="q3-1" value="T"> T</td>
                            <td class="radio-option"><input type="radio" name="q3-1" value="F"> F</td>
                        </tr>
                        <tr>
                            <td>2. She likes going to shopping centres.</td>
                            <td class="radio-option"><input type="radio" name="q3-2" value="T"> T</td>
                            <td class="radio-option"><input type="radio" name="q3-2" value="F"> F</td>
                        </tr>
                        <tr>
                            <td>3. She says it's easy to do shopping online.</td>
                            <td class="radio-option"><input type="radio" name="q3-3" value="T"> T</td>
                            <td class="radio-option"><input type="radio" name="q3-3" value="F"> F</td>
                        </tr>
                        <tr>
                            <td>4. If you don't like products, you can send them back.</td>
                            <td class="radio-option"><input type="radio" name="q3-4" value="T"> T</td>
                            <td class="radio-option"><input type="radio" name="q3-4" value="F"> F</td>
                        </tr>
                        <tr>
                            <td>5. Yasmin thinks that online shopping is sometimes difficult.</td>
                            <td class="radio-option"><input type="radio" name="q3-5" value="T"> T</td>
                            <td class="radio-option"><input type="radio" name="q3-5" value="F"> F</td>
                        </tr>
                    </table>
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 4 -->
            <div id="task-4" class="task-section">
                <h2 class="task-title">Zadanie 4 (5 p.)</h2>
                <p>Wybierz prawidłowe słowo lub frazę.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. They found some __________ on the window and the door.</p>
                    <select id="q4-1">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="fingerprints">fingerprints</option>
                        <option value="courts">courts</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>2. A __________ is a person who steals things from houses.</p>
                    <select id="q4-2">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="kidnapper">kidnapper</option>
                        <option value="burglar">burglar</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>3. Look at that graffiti on the wall – it was painted by a __________.</p>
                    <select id="q4-3">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="crime">crime</option>
                        <option value="vandal">vandal</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>4. The police __________ the man yesterday.</p>
                    <select id="q4-4">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="arrested">arrested</option>
                        <option value="stole">stole</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>5. It's important to have a strong password because __________ are dangerous.</p>
                    <select id="q4-5">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="hackers">hackers</option>
                        <option value="hacking">hacking</option>
                    </select>
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 5 -->
            <div id="task-5" class="task-section">
                <h2 class="task-title">Zadanie 5 (5 p.)</h2>
                <p>Przetłumacz na język angielski fragmenty zdań z nawiasów.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. __________ sugar do you take in your tea?</p>
                    <input type="text" id="q5-1" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="question">
                    <p>2. __________ in the bathroom now?</p>
                    <input type="text" id="q5-2" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="question">
                    <p>3. __________ along the corridors!</p>
                    <input type="text" id="q5-3" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="question">
                    <p>4. What is __________ language to learn?</p>
                    <input type="text" id="q5-4" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="question">
                    <p>5. They __________ to the cinema on Friday.</p>
                    <input type="text" id="q5-5" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 6 -->
            <div id="task-6" class="task-section">
                <h2 class="task-title">Zadanie 6 (5 p.)</h2>
                <p>Uzupełnij zdania odpowiednią formą czasownika.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. If you (feel) __________ dizzy, you should sit down and take a deep breath.</p>
                    <input type="text" id="q6-1" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>2. What __________ your mum (do) __________ right now?</p>
                    <input type="text" id="q6-2" placeholder="Wpisz pierwszą formę">
                    <input type="text" id="q6-3" placeholder="Wpisz drugą formę" style="margin-top: 10px;">
                </div>
                
                <div class="question">
                    <p>3. Mike is (intelligent) __________ than I am.</p>
                    <input type="text" id="q6-4" placeholder="Wpisz stopień wyższy">
                </div>
                
                <div class="question">
                    <p>4. __________ he (go) __________ to school every Saturday?</p>
                    <input type="text" id="q6-5" placeholder="Wpisz pierwszą formę">
                    <input type="text" id="q6-6" placeholder="Wpisz drugą formę" style="margin-top: 10px;">
                </div>
                
                <div class="question">
                    <p>5. I (be able to) __________ do it on my own.</p>
                    <input type="text" id="q6-7" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 7 -->
            <div id="task-7" class="task-section">
                <h2 class="task-title">Zadanie 7 (5 p.)</h2>
                <p>Uzupełnij dialogi odpowiednimi słowami.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. – Do you want to go to the shopping centre with me today?<br>
                       – I'm __________ I can't go. I have a test tomorrow.</p>
                    <input type="text" id="q7-1" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="question">
                    <p>2. – Can I take a photo of that man?<br>
                       – In my __________, you should ask him first.</p>
                    <input type="text" id="q7-2" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="question">
                    <p>3. – Horror stories are so boring!<br>
                       – I __________ agree! They're fantastic.</p>
                    <input type="text" id="q7-3" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="question">
                    <p>4. – Do you want a chocolate milkshake?<br>
                       – I would __________ have a banana milkshake.</p>
                    <input type="text" id="q7-4" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="question">
                    <p>5. – What __________ I do now?<br>
                       – Maybe talk to your parents?</p>
                    <input type="text" id="q7-5" placeholder="Wpisz brakujące słowo">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 8 -->
            <div id="task-8" class="task-section">
                <h2 class="task-title">Zadanie 8 (5 p.)</h2>
                <p>Wybierz właściwą odpowiedź.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. This box is not big __________ for the present.</p>
                    <select id="q8-1">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="too">too</option>
                        <option value="enough">enough</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>2. Yesterday at 11 o'clock I __________ to play a new song.</p>
                    <select id="q8-2">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="learnt">learnt</option>
                        <option value="was learning">was learning</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>3. He is running too fast. He is going to __________.</p>
                    <select id="q8-3">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="fall over">fall over</option>
                        <option value="falls over">falls over</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>4. Monika __________ her homework when her best friend came over.</p>
                    <select id="q8-4">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="did">did</option>
                        <option value="was doing">was doing</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>5. I hope they __________.</p>
                    <select id="q8-5">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="will come">will come</option>
                        <option value="are coming">are coming</option>
                    </select>
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 9 -->
            <div id="task-9" class="task-section">
                <h2 class="task-title">Zadanie 9 (5 p.)</h2>
                <p>Wybierz właściwą reakcję.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. Koleżanka pyta cię czy to dobry pomysł kupić kwiaty na imieniny mamy. Powiedz, że to dobry pomysł.</p>
                    <select id="q9-1">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. You should buy your mum some flowers.</option>
                        <option value="B">B. You can buy your mum some flowers.</option>
                        <option value="C">C. Yes, it would be a good idea to buy her flowers.</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>2. Powiedz koledze, że nie można tutaj grać w piłkę nożną.</p>
                    <select id="q9-2">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. You cannot play football here.</option>
                        <option value="B">B. You can play football here.</option>
                        <option value="C">C. Playing football is allowed here.</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>3. Ekspedientka pyta czy chcesz reklamówkę na Twoje zakupy. Powiedz, że tak.</p>
                    <select id="q9-3">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. Yes, here you are.</option>
                        <option value="B">B. Yes, I would one, please.</option>
                        <option value="C">C. I have got a bag.</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>4. Powiedz, że planujesz kupić nową książkę.</p>
                    <select id="q9-4">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. I am planning to buy a new book.</option>
                        <option value="B">B. I hope to buy a new book.</option>
                        <option value="C">C. I can't wait to buy a new book.</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>5. Kolega zaprasza cię na wyjście do kina. Niestety masz dużo nauki. Powiedz, że może innym razem.</p>
                    <select id="q9-5">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="A">A. Maybe some other time.</option>
                        <option value="B">B. I haven't got time.</option>
                        <option value="C">C. There isn't much time left.</option>
                    </select>
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 10 -->
            <div id="task-10" class="task-section">
                <h2 class="task-title">Zadanie 10 (5 p.)</h2>
                <p>Uzupełnij zdania używając czasu future simple.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. My best friend (have) __________ a surprise party next week.</p>
                    <input type="text" id="q10-1" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>2. It's so hot. I (open) __________ the window.</p>
                    <input type="text" id="q10-2" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>3. they (wait) __________ for us?</p>
                    <input type="text" id="q10-3" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>4. I think it (be) __________ a great party!</p>
                    <input type="text" id="q10-4" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>5. We (not catch) __________ that bus to the city centre.</p>
                    <input type="text" id="q10-5" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 11 -->
            <div id="task-11" class="task-section">
                <h2 class="task-title">Zadanie 11 (5 p.)</h2>
                <p>Uzupełnij luki wpisując czasowniki w nawiasach w czasie past simple lub past continuous.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. Mum and dad (not call) __________ me last week.</p>
                    <input type="text" id="q11-1" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>2. __________ you (have) __________ a good time yesterday?</p>
                    <input type="text" id="q11-2" placeholder="Wpisz pierwszą formę">
                    <input type="text" id="q11-3" placeholder="Wpisz drugą formę" style="margin-top: 10px;">
                </div>
                
                <div class="question">
                    <p>3. They (walk) __________ home when they saw a kitten in the middle of the street.</p>
                    <input type="text" id="q11-4" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>4. He (leave) __________ home late yesterday.</p>
                    <input type="text" id="q11-5" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>5. __________ Freddy (eat) __________ sushi at around 5:30 yesterday?</p>
                    <input type="text" id="q11-6" placeholder="Wpisz pierwszą formę">
                    <input type="text" id="q11-7" placeholder="Wpisz drugą formę" style="margin-top: 10px;">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 12 -->
            <div id="task-12" class="task-section">
                <h2 class="task-title">Zadanie 12 (5 p.)</h2>
                <p>Uzupełnij zdania wpisując w luki czasowniki w odpowiedniej formie. Użyj czasu past simple.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. __________ he (watch) __________ cartoons with his dad?</p>
                    <input type="text" id="q12-1" placeholder="Wpisz pierwszą formę">
                    <input type="text" id="q12-2" placeholder="Wpisz drugą formę" style="margin-top: 10px;">
                </div>
                
                <div class="question">
                    <p>2. __________ you (visit) __________ your friends on Wednesday?</p>
                    <input type="text" id="q12-3" placeholder="Wpisz pierwszą formę">
                    <input type="text" id="q12-4" placeholder="Wpisz drugą formę" style="margin-top: 10px;">
                </div>
                
                <div class="question">
                    <p>3. We (not play) __________ football at school.</p>
                    <input type="text" id="q12-5" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>4. I (walk) __________ the dog yesterday.</p>
                    <input type="text" id="q12-6" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="question">
                    <p>5. They (not like) __________ the concert at all.</p>
                    <input type="text" id="q12-7" placeholder="Wpisz formę czasownika">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 13 -->
            <div id="task-13" class="task-section">
                <h2 class="task-title">Zadanie 13 (5 p.)</h2>
                <p>Przetłumacz na język angielski fragmenty zdań z nawiasów.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. If you have a very difficult exam, you need to (uczysz się) __________ a lot before it.</p>
                    <input type="text" id="q13-1" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="question">
                    <p>2. (Jeśli masz) __________ a cold, you cough and have a runny nose.</p>
                    <input type="text" id="q13-2" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="question">
                    <p>3. If someone has a headache, they usually (biorą lekarstwo) __________.</p>
                    <input type="text" id="q13-3" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="question">
                    <p>4. (Jeśli mój tata ma) __________ a cough, he takes some syrup.</p>
                    <input type="text" id="q13-4" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="question">
                    <p>5. If you don't drink anything, you (jesteś spragniony) __________.</p>
                    <input type="text" id="q13-5" placeholder="Wpisz tłumaczenie">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 14 -->
            <div id="task-14" class="task-section">
                <h2 class="task-title">Zadanie 14 (5 p.)</h2>
                <p>Zakreśl prawidłowe słowo.</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. How do you celebrate __________ Children's Day?</p>
                    <select id="q14-1">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="a">a</option>
                        <option value="-">- (brak przedimka)</option>
                        <option value="the">the</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>2. Look, there is __________ dog in our living room.</p>
                    <select id="q14-2">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="a">a</option>
                        <option value="an">an</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>3. I hate eating __________ cucumbers.</p>
                    <select id="q14-3">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="-">- (brak przedimka)</option>
                        <option value="the">the</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>4. My favourite kind of __________ music is rock.</p>
                    <select id="q14-4">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="the">the</option>
                        <option value="-">- (brak przedimka)</option>
                    </select>
                </div>
                
                <div class="question">
                    <p>5. This is my new car. __________ car is really fast.</p>
                    <select id="q14-5">
                        <option value="">-- Wybierz odpowiedź --</option>
                        <option value="The">The</option>
                        <option value="A">A</option>
                    </select>
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Zadanie 15 -->
            <div id="task-15" class="task-section">
                <h2 class="task-title">Zadanie 15 (5 p.)</h2>
                <p>Uzupełnij luki wstawiając a, an, the, lub zero article (-).</p>
                <div class="points-info">5 punktów</div>
                
                <div class="question">
                    <p>1. I've got __________ hamster and two guinea pigs.</p>
                    <input type="text" id="q15-1" placeholder="Wpisz a, an, the lub -">
                </div>
                
                <div class="question">
                    <p>2. __________ summer is my favourite season - you can sunbathe and go surfing.</p>
                    <input type="text" id="q15-2" placeholder="Wpisz a, an, the lub -">
                </div>
                
                <div class="question">
                    <p>3. My birthday is in __________ May.</p>
                    <input type="text" id="q15-3" placeholder="Wpisz a, an, the lub -">
                </div>
                
                <div class="question">
                    <p>4. There is a new boy in our class. __________ boy's name is Timmy.</p>
                    <input type="text" id="q15-4" placeholder="Wpisz a, an, the lub -">
                </div>
                
                <div class="question">
                    <p>5. I want to buy __________ orange to make some fresh juice.</p>
                    <input type="text" id="q15-5" placeholder="Wpisz a, an, the lub -">
                </div>
                
                <div class="navigation">
                    <button class="nav-button" onclick="prevTask()">
                        <i class="fas fa-arrow-left"></i> Poprzednie
                    </button>
                    <button class="nav-button" onclick="nextTask()">
                        Następne <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
            
            <!-- Komunikat ukończenia -->
            <div id="completion-section" class="task-section">
                <div class="completion-message">
                    <h2><i class="fas fa-check-circle"></i> Test ukończony!</h2>
                    <p>Dziękujemy za wypełnienie testu diagnozującego z języka angielskiego.</p>
                    <p>Twoje odpowiedzi zostały zapisane i oczekują na ocenę przez nauczyciela.</p>
                    <p>Łączna liczba punktów: <strong>75</strong></p>
                    <div id="save-message" class="success-message" style="display: none;">
                        <i class="fas fa-check"></i> Odpowiedzi zostały pomyślnie zapisane w bazie danych.
                    </div>
                    <div id="save-error" class="error-message" style="display: none;">
                        <i class="fas fa-exclamation-triangle"></i> Wystąpił błąd podczas zapisywania odpowiedzi.
                    </div>
                    <button class="nav-button" onclick="exportAnswers()" style="margin-top: 20px;">
                        <i class="fas fa-download"></i> Eksportuj odpowiedzi (backup)
                    </button>
                </div>
            </div>
            
            <!-- Loading indicator -->
            <div id="loading" class="loading">
                <i class="fas fa-spinner fa-spin"></i>
                <p>Zapisywanie odpowiedzi do bazy danych...</p>
            </div>
        </div>
        
        <!-- Pasek postępu -->
        <div class="progress-bar" id="progress-bar">
            <!-- Zostanie wypełnione dynamicznie przez JavaScript -->
        </div>
    </div>
    
    <!-- Audio elementy (lokalne pliki) -->
    <audio id="audio-file-1" src="nagranie1.mp3" preload="auto"></audio>
    <audio id="audio-file-2" src="nagranie2.mp3" preload="auto"></audio>
    <audio id="audio-file-3" src="nagranie3.mp3" preload="auto"></audio>
    
    <!-- Supabase JS -->
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
    
    <script>
        // ================================
        // INICJALIZACJA SUPABASE
        // ================================
        const SUPABASE_URL = 'https://atopppaefkbdmrsyecun.supabase.co';
        const SUPABASE_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImF0b3BwcGFlZmtiZG1yc3llY3VuIiwicm9sZSI6ImFub24iLCJpYXQiOjE3Njk4OTYxMTUsImV4cCI6MjA4NTQ3MjExNX0.hp3en5PoQjUxsh_j4tWfCE1NRds5cZkLdbmQx0_K7cU';
        
        // Inicjalizacja Supabase
        let supabaseClient;
        try {
            supabaseClient = window.supabase.createClient(SUPABASE_URL, SUPABASE_KEY);
            console.log('Supabase zainicjalizowany pomyślnie');
        } catch (error) {
            console.error('Błąd inicjalizacji Supabase:', error);
            // Kontynuuj bez Supabase - użyjemy localStorage jako fallback
        }
        
        // ================================
        // ZMIENNE GLOBALNE
        // ================================
        let currentTask = 0;
        let studentName = '';
        const totalTasks = 15;
        const audioCounters = [3, 3, 3];
        
        // Dane odpowiedzi dla wszystkich 15 zadań
        let answers = {
            student_name: '',
            timestamp: '',
            test_name: 'DIAGNOZA Z J. ANGIELSKIEGO KLASA 7',
            test_code: 'DIAG-ENG-7-2024',
            total_points: 75,
            task_1: {}, task_2: {}, task_3: {}, task_4: {}, task_5: {},
            task_6: {}, task_7: {}, task_8: {}, task_9: {}, task_10: {},
            task_11: {}, task_12: {}, task_13: {}, task_14: {}, task_15: {}
        };
        
        // Inicjalizacja po załadowaniu strony
        document.addEventListener('DOMContentLoaded', function() {
            console.log('Strona załadowana - pełny test diagnozy (15 zadań)');
            
            // Inicjalizacja paska postępu
            initProgressBar();
            
            // Ustaw focus na polu imienia
            document.getElementById('student-name').focus();
            
            // Przywróć zapisane odpowiedzi z localStorage jeśli istnieją
            restoreFromLocalStorage();
            
            // Dodaj obsługę klawisza Enter w polu imienia
            document.getElementById('student-name').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    startTest();
                }
            });
            
            // Dodaj nasłuchiwanie na zmiany w odpowiedziach
            setupAnswerListeners();
        });
        
        // Inicjalizacja paska postępu
        function initProgressBar() {
            const progressBar = document.getElementById('progress-bar');
            if (!progressBar) return;
            
            // Dodaj punkt dla danych ucznia
            const studentDot = document.createElement('div');
            studentDot.className = 'progress-dot current';
            studentDot.innerHTML = '<i class="fas fa-user"></i>';
            studentDot.dataset.task = '0';
            studentDot.onclick = () => navigateToTask(0);
            progressBar.appendChild(studentDot);
            
            // Dodaj punkty dla zadań (1-15)
            for (let i = 1; i <= totalTasks; i++) {
                const dot = document.createElement('div');
                dot.className = 'progress-dot';
                dot.textContent = i;
                dot.dataset.task = i.toString();
                dot.onclick = () => navigateToTask(i);
                progressBar.appendChild(dot);
            }
            
            // Dodaj przycisk zapisz/dalej
            const saveButton = document.createElement('button');
            saveButton.id = 'save-progress-btn';
            saveButton.className = 'nav-button save-button';
            saveButton.textContent = 'Zapisz';
            saveButton.onclick = saveAllAnswersToSupabase;
            progressBar.appendChild(saveButton);
        }
        
        // Rozpocznij test
        function startTest() {
            console.log('Przycisk "Rozpocznij test" kliknięty!');
            
            const nameInput = document.getElementById('student-name');
            const errorElement = document.getElementById('student-error');
            
            if (!nameInput.value.trim()) {
                if (errorElement) {
                    errorElement.style.display = 'block';
                    errorElement.textContent = 'Proszę podać imię i nazwisko';
                    setTimeout(() => {
                        errorElement.style.display = 'none';
                    }, 3000);
                }
                nameInput.focus();
                return;
            }
            
            if (errorElement) {
                errorElement.style.display = 'none';
            }
            
            studentName = nameInput.value.trim();
            answers.student_name = studentName;
            answers.timestamp = new Date().toISOString();
            
            // Zapisz w localStorage
            localStorage.setItem('diagnoza_student_name', studentName);
            
            console.log('Uczeń:', studentName);
            console.log('Przechodzę do zadania 1');
            
            // Przejdź do pierwszego zadania
            navigateToTask(1);
        }
        
        // Nawigacja między zadaniami
        function navigateToTask(taskNumber) {
            console.log('Przechodzę do zadania:', taskNumber);
            
            // Zapisz aktualne odpowiedzi przed przejściem
            saveCurrentTaskAnswers();
            
            // Ukryj wszystkie sekcje
            document.querySelectorAll('.task-section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Pokaż wybraną sekcję
            if (taskNumber === 0) {
                document.getElementById('student-section').classList.add('active');
            } else if (taskNumber <= totalTasks) {
                const taskElement = document.getElementById(`task-${taskNumber}`);
                if (taskElement) {
                    taskElement.classList.add('active');
                }
            } else {
                document.getElementById('completion-section').classList.add('active');
            }
            
            // Zaktualizuj aktualne zadanie
            currentTask = taskNumber;
            
            // Zaktualizuj pasek postępu
            updateProgressBar();
            
            // Zaktualizuj przycisk zapisz/dalej
            updateSaveButton();
        }
        
        // Poprzednie zadanie
        function prevTask() {
            if (currentTask > 1) {
                navigateToTask(currentTask - 1);
            }
        }
        
        // Następne zadanie
        function nextTask() {
            if (currentTask < totalTasks) {
                navigateToTask(currentTask + 1);
            } else if (currentTask === totalTasks) {
                navigateToTask(totalTasks + 1);
            }
        }
        
        // Aktualizuj pasek postępu
        function updateProgressBar() {
            const dots = document.querySelectorAll('.progress-dot');
            
            dots.forEach((dot) => {
                const taskNum = parseInt(dot.dataset.task);
                dot.classList.remove('active', 'current', 'visited', 'completed');
                
                if (taskNum === currentTask) {
                    dot.classList.add('current');
                } else if (taskNum === 0) {
                    dot.classList.add('visited');
                } else {
                    const taskKey = `task_${taskNum}`;
                    if (answers[taskKey]) {
                        const isCompleted = isTaskCompleted(taskNum);
                        if (isCompleted) {
                            dot.classList.add('completed');
                        } else {
                            dot.classList.add('visited');
                        }
                    }
                }
            });
        }
        
        // Aktualizuj przycisk zapisz/dalej
        function updateSaveButton() {
            const saveButton = document.getElementById('save-progress-btn');
            if (!saveButton) return;
            
            const allCompleted = checkAllTasksCompleted();
            
            if (allCompleted && currentTask > totalTasks) {
                saveButton.textContent = 'Zapisano';
                saveButton.disabled = true;
            } else if (allCompleted) {
                saveButton.textContent = 'Dalej';
                saveButton.onclick = () => {
                    if (currentTask <= totalTasks) {
                        nextTask();
                    }
                };
            } else {
                saveButton.textContent = 'Zapisz do bazy';
                saveButton.onclick = saveAllAnswersToSupabase;
            }
        }
        
        // Sprawdź czy wszystkie zadania są ukończone
        function checkAllTasksCompleted() {
            for (let i = 1; i <= totalTasks; i++) {
                if (!isTaskCompleted(i)) {
                    return false;
                }
            }
            return true;
        }
        
        // Sprawdź czy zadanie jest ukończone
        function isTaskCompleted(taskNumber) {
            const taskKey = `task_${taskNumber}`;
            if (!answers[taskKey]) return false;
            
            const questionCount = getQuestionCountForTask(taskNumber);
            for (let q = 1; q <= questionCount; q++) {
                if (!answers[taskKey][`q${q}`]) {
                    return false;
                }
            }
            return true;
        }
        
        // Pobierz liczbę pytań w zadaniu
        function getQuestionCountForTask(taskNumber) {
            const counts = {
                1: 5, 2: 5, 3: 5, 4: 5, 5: 5,
                6: 7,  // Zadanie 6 ma 7 pól (ale 5 pytań)
                7: 5, 8: 5, 9: 5, 10: 5,
                11: 7, // Zadanie 11 ma 7 pól (ale 5 pytań)
                12: 7, // Zadanie 12 ma 7 pól (ale 5 pytań)
                13: 5, 14: 5, 15: 5
            };
            return counts[taskNumber] || 5; // Domyślnie 5
        }
        
        // Zapisz odpowiedzi z aktualnego zadania
        function saveCurrentTaskAnswers() {
            if (currentTask === 0 || currentTask > totalTasks) return;
            
            const taskKey = `task_${currentTask}`;
            if (!answers[taskKey]) {
                answers[taskKey] = {};
            }
            
            const questionCount = getQuestionCountForTask(currentTask);
            for (let q = 1; q <= questionCount; q++) {
                const elementId = `q${currentTask}-${q}`;
                const element = document.getElementById(elementId);
                
                if (element) {
                    if (element.type === 'radio') {
                        const checkedRadio = document.querySelector(`input[name="${elementId}"]:checked`);
                        answers[taskKey][`q${q}`] = checkedRadio ? checkedRadio.value : '';
                    } else {
                        answers[taskKey][`q${q}`] = element.value.trim();
                    }
                }
            }
            
            // Zapisz w localStorage
            saveToLocalStorage();
            
            // Aktualizuj pasek postępu
            updateProgressBar();
            updateSaveButton();
        }
        
        // Odtwarzanie nagrań (lokalne pliki)
        function playAudio(audioNumber) {
            const audioElement = document.getElementById(`audio-file-${audioNumber}`);
            const counterElement = document.getElementById(`audio-counter-${audioNumber}`);
            const playButton = document.getElementById(`play-audio-${audioNumber}`);
            
            if (audioCounters[audioNumber - 1] <= 0) {
                playButton.disabled = true;
                playButton.innerHTML = '<i class="fas fa-ban"></i> Limit odtworzeń wyczerpany';
                return;
            }
            
            audioElement.play().catch(e => {
                console.log('Błąd odtwarzania audio:', e);
                alert('Nie można odtworzyć nagrania. Sprawdź czy plik nagranie' + audioNumber + '.mp3 istnieje w folderze.');
            });
            
            // Dla prawdziwego odtwarzania
            audioElement.onended = function() {
                audioCounters[audioNumber - 1]--;
                counterElement.textContent = audioCounters[audioNumber - 1];
                
                if (audioCounters[audioNumber - 1] <= 0) {
                    playButton.disabled = true;
                    playButton.innerHTML = '<i class="fas fa-ban"></i> Limit odtworzeń wyczerpany';
                }
            };
        }
        
        // ZAPISZ WSZYSTKIE ODPOWIEDZI DO SUPABASE
        async function saveAllAnswersToSupabase() {
            console.log('Zapisywanie odpowiedzi do Supabase...');
            
            // Pokaż ładowanie
            document.getElementById('loading').style.display = 'block';
            document.getElementById('save-message').style.display = 'none';
            document.getElementById('save-error').style.display = 'none';
            
            try {
                // Sprawdź czy Supabase jest zainicjalizowany
                if (!supabaseClient) {
                    throw new Error('Brak połączenia z Supabase');
                }
                
                // Przygotuj dane do wysłania
                const testData = {
                    student_name: answers.student_name,
                    test_name: answers.test_name,
                    test_code: answers.test_code,
                    answers: answers,
                    total_points: answers.total_points,
                    completed_at: new Date().toISOString(),
                    submitted_at: new Date().toISOString(),
                    status: 'submitted'
                };
                
                console.log('Wysyłanie danych do Supabase:', testData);
                
                // Wyślij dane do Supabase
                const { data, error } = await supabaseClient
                    .from('student_answers')
                    .insert([testData]);
                
                if (error) {
                    throw error;
                }
                
                // Sukces
                console.log('Dane zapisane w Supabase:', data);
                
                // Ukryj ładowanie
                document.getElementById('loading').style.display = 'none';
                
                // Pokaż komunikat sukcesu
                document.getElementById('save-message').style.display = 'block';
                document.getElementById('save-message').innerHTML = 
                    '<i class="fas fa-check"></i> Odpowiedzi zostały pomyślnie zapisane w bazie danych Supabase!';
                
                // Zaktualizuj przycisk
                updateSaveButton();
                
                // Wyczyść localStorage po udanym zapisie
                localStorage.removeItem('diagnoza_full_answers');
                localStorage.removeItem('diagnoza_student_name');
                localStorage.removeItem('diagnoza_last_save');
                
                // Przejdź do ekranu ukończenia jeśli wszystkie zadania wypełnione
                if (checkAllTasksCompleted()) {
                    setTimeout(() => {
                        navigateToTask(totalTasks + 1);
                    }, 2000);
                }
                
            } catch (error) {
                console.error('Błąd zapisu do Supabase:', error);
                
                // Ukryj ładowanie
                document.getElementById('loading').style.display = 'none';
                
                // Pokaż komunikat błędu
                document.getElementById('save-error').style.display = 'block';
                document.getElementById('save-error').innerHTML = 
                    '<i class="fas fa-exclamation-triangle"></i> Błąd połączenia z bazą danych. Odpowiedzi zapisane lokalnie.';
                
                // Fallback: zapisz w localStorage
                localStorage.setItem('diagnoza_backup_' + Date.now(), JSON.stringify(answers));
                
                alert('Odpowiedzi zostały zapisane lokalnie. Skontaktuj się z nauczycielem.');
            }
        }
        
        // Eksportuj odpowiedzi do pliku (backup)
        function exportAnswers() {
            const dataStr = JSON.stringify(answers, null, 2);
            const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
            
            const exportFileDefaultName = `odpowiedzi_${answers.student_name}_${new Date().toISOString().slice(0,10)}.json`;
            
            const linkElement = document.createElement('a');
            linkElement.setAttribute('href', dataUri);
            linkElement.setAttribute('download', exportFileDefaultName);
            linkElement.click();
            
            alert('Odpowiedzi wyeksportowane do pliku JSON!');
        }
        
        // Zapisz odpowiedzi do localStorage
        function saveToLocalStorage() {
            try {
                localStorage.setItem('diagnoza_full_answers', JSON.stringify(answers));
                localStorage.setItem('diagnoza_last_save', new Date().toISOString());
            } catch (e) {
                console.log('Błąd zapisu do localStorage:', e);
            }
        }
        
        // Przywróć odpowiedzi z localStorage
        function restoreFromLocalStorage() {
            try {
                const savedName = localStorage.getItem('diagnoza_student_name');
                const savedAnswers = localStorage.getItem('diagnoza_full_answers');
                
                if (savedName) {
                    document.getElementById('student-name').value = savedName;
                }
                
                if (savedAnswers) {
                    answers = JSON.parse(savedAnswers);
                    
                    for (let taskNum = 1; taskNum <= totalTasks; taskNum++) {
                        const taskKey = `task_${taskNum}`;
                        if (answers[taskKey]) {
                            const questionCount = getQuestionCountForTask(taskNum);
                            for (let q = 1; q <= questionCount; q++) {
                                const elementId = `q${taskNum}-${q}`;
                                const element = document.getElementById(elementId);
                                const answerValue = answers[taskKey][`q${q}`];
                                
                                if (element && answerValue) {
                                    if (element.type === 'radio') {
                                        const radioToCheck = document.querySelector(`input[name="${elementId}"][value="${answerValue}"]`);
                                        if (radioToCheck) {
                                            radioToCheck.checked = true;
                                        }
                                    } else {
                                        element.value = answerValue;
                                    }
                                }
                            }
                        }
                    }
                    
                    updateProgressBar();
                    updateSaveButton();
                }
            } catch (e) {
                console.log('Błąd odczytu z localStorage:', e);
            }
        }
        
        // Ustaw nasłuchiwanie zmian odpowiedzi dla wszystkich zadań
        function setupAnswerListeners() {
            for (let taskNum = 1; taskNum <= totalTasks; taskNum++) {
                const questionCount = getQuestionCountForTask(taskNum);
                for (let q = 1; q <= questionCount; q++) {
                    const elementId = `q${taskNum}-${q}`;
                    const element = document.getElementById(elementId);
                    
                    if (element) {
                        if (element.type === 'radio') {
                            const radios = document.querySelectorAll(`input[name="${elementId}"]`);
                            radios.forEach(radio => {
                                radio.addEventListener('change', saveCurrentTaskAnswers);
                            });
                        } else {
                            element.addEventListener('input', saveCurrentTaskAnswers);
                            element.addEventListener('change', saveCurrentTaskAnswers);
                        }
                    }
                }
            }
        }
        
        // Funkcja do pobrania wszystkich odpowiedzi (dla nauczyciela)
        function getAllAnswers() {
            return answers;
        }
    </script>
</body>
</html>
