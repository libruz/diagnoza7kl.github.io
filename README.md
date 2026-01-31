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
        
        input[type="text"], select {
            padding: 10px 15px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            width: 100%;
            transition: border-color 0.3s;
        }
        
        input[type="text"]:focus, select:focus {
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
            <div class="subtitle">Klasa 7 - Test diagnozujący</div>
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
                <h2 class="task-title">Zadanie 1</h2>
                <p>Posłuchaj wypowiedzi (A–E) i dopasuj zdania do osób mówiących (1–5).</p>
                
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
                <h2 class="task-title">Zadanie 2</h2>
                <p>Wysłuchaj nagrania i uzupełnij zdania. W każdą lukę należy wpisać jeden wyraz.</p>
                
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
                <h2 class="task-title">Zadanie 3</h2>
                <p>Posłuchaj nagrania i określ czy podane zdania są prawdziwe – True (T) czy fałszywe – False (F).</p>
                
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
                <h2 class="task-title">Zadanie 4</h2>
                <p>Wybierz prawidłowe słowo lub frazę.</p>
                
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
                <h2 class="task-title">Zadanie 5</h2>
                <p>Przetłumacz na język angielski fragmenty zdań z nawiasów.</p>
                
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
            
            <!-- Komunikat ukończenia -->
            <div id="completion-section" class="task-section">
                <div class="completion-message">
                    <h2><i class="fas fa-check-circle"></i> Test ukończony!</h2>
                    <p>Dziękujemy za wypełnienie testu diagnozującego.</p>
                    <p>Twoje odpowiedzi zostały zapisane i oczekują na ocenę przez nauczyciela.</p>
                    <p>Możesz zamknąć tę stronę.</p>
                    <div id="save-message" class="success-message" style="display: none;">
                        <i class="fas fa-check"></i> Odpowiedzi zostały pomyślnie zapisane w bazie danych.
                    </div>
                    <div id="save-error" class="error-message" style="display: none;">
                        <i class="fas fa-exclamation-triangle"></i> Wystąpił błąd podczas zapisywania odpowiedzi.
                    </div>
                </div>
            </div>
            
            <!-- Loading indicator -->
            <div id="loading" class="loading">
                <i class="fas fa-spinner fa-spin"></i>
                <p>Zapisywanie odpowiedzi...</p>
            </div>
        </div>
        
        <!-- Pasek postępu -->
        <div class="progress-bar" id="progress-bar">
            <!-- Zostanie wypełnione dynamicznie przez JavaScript -->
        </div>
    </div>
    
    <!-- Audio elementy (ukryte) -->
    <audio id="audio-file-1" preload="auto"></audio>
    <audio id="audio-file-2" preload="auto"></audio>
    <audio id="audio-file-3" preload="auto"></audio>
    
    <script>
        // ================================
        // PROSTE ROZWIĄZANIE BEZ SUPABASE
        // ================================
        
        // Zmienne globalne
        let currentTask = 0;
        let studentName = '';
        const totalTasks = 5;
        const audioCounters = [3, 3, 3];
        
        // Dane odpowiedzi
        let answers = {
            student_name: '',
            task_1: {},
            task_2: {},
            task_3: {},
            task_4: {},
            task_5: {}
        };
        
        // Inicjalizacja po załadowaniu strony
        document.addEventListener('DOMContentLoaded', function() {
            console.log('Strona załadowana - test diagnozy');
            
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
            
            // Dodaj punkty dla zadań
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
            saveButton.onclick = saveAllAnswers;
            progressBar.appendChild(saveButton);
        }
        
        // Rozpocznij test - TERAZ DZIAŁA POPRAWNIE!
        function startTest() {
            console.log('Przycisk "Rozpocznij test" kliknięty!');
            
            const nameInput = document.getElementById('student-name');
            const errorElement = document.getElementById('student-error');
            
            if (!nameInput.value.trim()) {
                // Pokaż błąd
                if (errorElement) {
                    errorElement.style.display = 'block';
                    errorElement.textContent = 'Proszę podać imię i nazwisko';
                    // Ukryj błąd po 3 sekundach
                    setTimeout(() => {
                        errorElement.style.display = 'none';
                    }, 3000);
                }
                nameInput.focus();
                return;
            }
            
            // Ukryj błąd jeśli był pokazany
            if (errorElement) {
                errorElement.style.display = 'none';
            }
            
            studentName = nameInput.value.trim();
            answers.student_name = studentName;
            
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
                saveButton.textContent = 'Zapisz';
                saveButton.onclick = saveAllAnswers;
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
            const counts = {1: 5, 2: 5, 3: 5, 4: 5, 5: 5};
            return counts[taskNumber] || 0;
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
        
        // Odtwarzanie nagrań z fallback
        function playAudio(audioNumber) {
            const audioElement = document.getElementById(`audio-file-${audioNumber}`);
            const counterElement = document.getElementById(`audio-counter-${audioNumber}`);
            const playButton = document.getElementById(`play-audio-${audioNumber}`);
            
            // Testowe nagrania online
            const audioFiles = {
                1: 'https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3',
                2: 'https://www.soundhelix.com/examples/mp3/SoundHelix-Song-2.mp3',
                3: 'https://www.soundhelix.com/examples/mp3/SoundHelix-Song-3.mp3'
            };
            
            if (audioCounters[audioNumber - 1] <= 0) {
                playButton.disabled = true;
                playButton.innerHTML = '<i class="fas fa-ban"></i> Limit odtworzeń wyczerpany';
                return;
            }
            
            if (!audioElement.src) {
                audioElement.src = audioFiles[audioNumber];
            }
            
            audioElement.play().catch(e => {
                console.log('Błąd odtwarzania audio:', e);
                // Symuluj odtwarzanie dla testów
                audioCounters[audioNumber - 1]--;
                counterElement.textContent = audioCounters[audioNumber - 1];
                
                if (audioCounters[audioNumber - 1] <= 0) {
                    playButton.disabled = true;
                    playButton.innerHTML = '<i class="fas fa-ban"></i> Limit odtworzeń wyczerpany';
                }
                
                alert('Nagranie odtworzone (symulacja). W prawdziwym teście usłyszysz pytania.');
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
        
        // Zapisz wszystkie odpowiedzi (bez Supabase - tylko localStorage)
        function saveAllAnswers() {
            console.log('Zapisywanie odpowiedzi...');
            
            // Pokaż ładowanie
            document.getElementById('loading').style.display = 'block';
            
            // Symuluj zapis
            setTimeout(() => {
                // Ukryj ładowanie
                document.getElementById('loading').style.display = 'none';
                
                // Pokaż komunikat sukcesu
                document.getElementById('save-message').style.display = 'block';
                
                // Zaktualizuj przycisk
                updateSaveButton();
                
                console.log('Odpowiedzi zapisane:', answers);
                
                // Wyświetl podsumowanie w konsoli
                console.log('=== PODSUMOWANIE TESTU ===');
                console.log('Uczeń:', answers.student_name);
                console.log('Odpowiedzi:', answers);
                
            }, 1000);
        }
        
        // Zapisz odpowiedzi do localStorage
        function saveToLocalStorage() {
            try {
                localStorage.setItem('diagnoza_answers', JSON.stringify(answers));
            } catch (e) {
                console.log('Błąd zapisu do localStorage:', e);
            }
        }
        
        // Przywróć odpowiedzi z localStorage
        function restoreFromLocalStorage() {
            try {
                const savedName = localStorage.getItem('diagnoza_student_name');
                const savedAnswers = localStorage.getItem('diagnoza_answers');
                
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
        
        // Ustaw nasłuchiwanie zmian odpowiedzi
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
            return {
                student: answers.student_name,
                answers: answers,
                timestamp: new Date().toISOString()
            };
        }
    </script>
</body>
</html>
