<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Brain and Mind Academy - Digital SAT Practice Test 5 Math Learning Sheet</title>
    <!-- Desmos API Script -->
    <script src="https://www.desmos.com/api/v1.8/calculator.js?apiKey=d2822b107a6c49f6a00a221957776319"></script>
    <style>
        :root {
            --primary-header: #1e3a8a;
            --header-gradient: linear-gradient(135deg, #0f172a 0%, #1e3a8a 100%);
            --accent-gold: #d97706;
            --accent-gold-light: #fcd34d;
            --correct-green: #059669;
            --correct-bg: #d1fae5;
            --incorrect-red: #dc2626;
            --incorrect-bg: #fee2e2;
            --skipped-orange: #f59e0b;
            --skipped-bg: #fef3c7;
            --bg-body: #f8fafc;
            --text-dark: #1e293b;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --card-bg: #ffffff;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-body);
            color: var(--text-dark);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        header {
            background: var(--header-gradient);
            color: white;
            padding: 1.25rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .brand-title {
            font-size: 1.5rem;
            font-weight: 700;
            letter-spacing: 0.5px;
            color: #ffffff;
        }

        .brand-subtitle {
            font-size: 0.9rem;
            color: var(--accent-gold-light);
            font-weight: 600;
            margin-top: 2px;
        }

        .user-info {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .user-email {
            font-size: 0.85rem;
            background: rgba(255, 255, 255, 0.15);
            padding: 0.4rem 0.8rem;
            border-radius: 6px;
        }

        .btn {
            padding: 0.6rem 1.25rem;
            border: none;
            border-radius: 6px;
            font-weight: 600;
            font-size: 0.9rem;
            cursor: pointer;
            transition: all 0.2s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .btn-sm {
            padding: 0.4rem 0.85rem;
            font-size: 0.8rem;
            border-radius: 4px;
        }

        .btn-primary { background-color: var(--primary-header); color: white; }
        .btn-primary:hover { background-color: #172554; }
        .btn-gold { background-color: var(--accent-gold); color: white; }
        .btn-gold:hover { background-color: #b45309; }
        .btn-outline { background: transparent; border: 1.5px solid var(--border-color); color: var(--text-dark); }
        .btn-outline:hover { background-color: #f1f5f9; }
        .btn-danger { background-color: var(--incorrect-red); color: white; }
        .btn-danger:hover { background-color: #b91c1c; }
        .btn-success { background-color: var(--correct-green); color: white; }
        .btn-success:hover { background-color: #047857; }

        .screen {
            display: none;
            padding: 2rem;
            max-width: 1400px;
            margin: 0 auto;
            width: 100%;
            flex: 1;
        }

        .screen.active { display: block; }

        #auth-screen {
            max-width: 480px;
            margin: auto;
            padding-top: 4rem;
        }

        .auth-card {
            background: var(--card-bg);
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.05);
            border: 1px solid var(--border-color);
            text-align: center;
        }

        .auth-card h2 { margin-bottom: 0.5rem; color: var(--primary-header); }
        .auth-card p { color: var(--text-muted); font-size: 0.9rem; margin-bottom: 1.5rem; }

        .form-group { margin-bottom: 1.25rem; text-align: left; }
        .form-group label { display: block; margin-bottom: 0.4rem; font-size: 0.85rem; font-weight: 600; }
        .form-group input, .form-group select {
            width: 100%; padding: 0.75rem; border: 1px solid var(--border-color);
            border-radius: 6px; font-size: 1rem; outline: none; background: white;
        }
        .form-group input:focus, .form-group select:focus {
            border-color: var(--primary-header);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.1);
        }

        .quiz-container {
            display: grid;
            grid-template-columns: 1fr 380px;
            gap: 2rem;
            align-items: start;
        }

        .quiz-card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 2rem;
            border: 1px solid var(--border-color);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
        }

        .quiz-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid var(--bg-body);
            padding-bottom: 1rem;
            margin-bottom: 1.5rem;
        }

        .q-badge {
            background: #eff6ff;
            color: var(--primary-header);
            font-weight: 700;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.85rem;
        }

        .q-title {
            font-size: 1.2rem;
            line-height: 1.5;
            margin-bottom: 0.75rem;
            font-weight: 700;
            color: var(--primary-header);
        }

        .problem-statement {
            background: #f1f5f9;
            border-left: 4px solid var(--primary-header);
            padding: 1rem 1.25rem;
            border-radius: 6px;
            font-size: 1rem;
            line-height: 1.6;
            margin-bottom: 1.5rem;
            font-weight: 600;
        }

        .scale-graph-container {
            display: flex;
            justify-content: center;
            align-items: center;
            background: #ffffff;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 1rem;
            margin: 1rem 0 1.5rem 0;
            overflow-x: auto;
        }

        .quiz-switch-bar {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .switch-tab {
            padding: 0.5rem 1rem;
            border: 1.5px solid var(--border-color);
            background: white;
            border-radius: 6px;
            font-weight: 700;
            font-size: 0.85rem;
            cursor: pointer;
            color: var(--text-dark);
            transition: all 0.2s ease;
        }

        .switch-tab.active-tab {
            background: var(--primary-header);
            color: white;
            border-color: var(--primary-header);
        }

        /* Micro Step Blocks */
        .step-block {
            background: #f8fafc;
            border: 1.5px solid var(--border-color);
            border-radius: 10px;
            padding: 1.25rem;
            margin-bottom: 1.5rem;
            transition: all 0.3s ease;
        }

        .step-block.locked {
            opacity: 0.4;
            pointer-events: none;
            filter: grayscale(0.8);
        }

        .step-block.active-step {
            border-color: var(--primary-header);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.1);
        }

        .step-block.completed-step {
            border-color: var(--correct-green);
            background-color: #f0fdf4;
        }

        .step-block.skipped-step {
            border-color: var(--skipped-orange);
            background-color: var(--skipped-bg);
        }

        .step-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 0.75rem;
        }

        .step-tag {
            font-weight: 700;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            color: var(--accent-gold);
        }

        .completed-step .step-tag { color: var(--correct-green); }
        .skipped-step .step-tag { color: var(--skipped-orange); }

        .step-prompt {
            font-size: 0.95rem;
            font-weight: 600;
            margin-bottom: 1rem;
            line-height: 1.5;
        }

        .step-actions {
            display: flex;
            gap: 0.5rem;
            margin-top: 1rem;
            padding-top: 0.75rem;
            border-top: 1px dashed var(--border-color);
        }

        .step-options-list {
            display: flex;
            flex-direction: column;
            gap: 0.6rem;
            margin-bottom: 0.5rem;
        }

        .step-option-item {
            display: flex;
            align-items: center;
            padding: 0.75rem 1rem;
            border: 1.5px solid var(--border-color);
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.2s ease;
            background: white;
            font-size: 0.95rem;
            font-weight: 600;
        }

        .step-option-item:hover:not(.disabled) {
            border-color: var(--primary-header);
            background-color: #eff6ff;
        }

        .step-option-item.selected {
            border-color: var(--primary-header);
            background-color: #eff6ff;
        }

        .step-option-item.correct {
            border-color: var(--correct-green);
            background-color: var(--correct-bg);
            color: #065f46;
        }

        .step-option-item.incorrect {
            border-color: var(--incorrect-red);
            background-color: var(--incorrect-bg);
            color: #991b1b;
        }

        .step-option-item.disabled { cursor: default; }

        .step-opt-prefix {
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background: #e2e8f0;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 0.75rem;
            margin-right: 0.75rem;
            flex-shrink: 0;
        }

        .step-option-item.selected .step-opt-prefix { background: var(--primary-header); color: white; }
        .step-option-item.correct .step-opt-prefix { background: var(--correct-green); color: white; }
        .step-option-item.incorrect .step-opt-prefix { background: var(--incorrect-red); color: white; }

        .action-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-top: 1.5rem;
            border-top: 1px solid var(--border-color);
        }

        .rationale-box {
            margin-top: 1.5rem;
            padding: 1.25rem;
            border-radius: 8px;
            background: #f1f5f9;
            border-left: 4px solid var(--primary-header);
        }

        .rationale-title { font-weight: 700; color: var(--primary-header); margin-bottom: 0.5rem; }

        .quiz-sidebar {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            position: sticky;
            top: 2rem;
        }

        .sidebar-card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 1.5rem;
            border: 1px solid var(--border-color);
        }

        .sidebar-title {
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--primary-header);
        }

        .legend-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
            font-size: 0.8rem;
        }

        .legend-item { display: flex; align-items: center; gap: 0.4rem; }
        .legend-dot { width: 12px; height: 12px; border-radius: 3px; }
        .dot-active { border: 2px solid var(--primary-header); background: transparent; }
        .dot-attempted { background: var(--correct-green); }
        .dot-skipped { background: var(--skipped-orange); }
        .dot-unvisited { background: #cbd5e1; }

        .question-grid {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 0.45rem;
            max-height: 220px;
            overflow-y: auto;
        }

        .grid-btn {
            aspect-ratio: 1; border: 1px solid var(--border-color); background: #f8fafc;
            color: var(--text-dark); border-radius: 6px; font-weight: 600; font-size: 0.85rem;
            cursor: pointer; transition: all 0.15s ease;
        }

        .grid-btn.active { border: 2px solid var(--primary-header); color: var(--primary-header); font-weight: 800; background: #eff6ff; }
        .grid-btn.attempted { background: var(--correct-green); color: white; border-color: var(--correct-green); }
        .grid-btn.skipped { background: var(--skipped-orange); color: white; border-color: var(--skipped-orange); }

        /* Calculator Styling */
        .calc-display {
            width: 100%;
            padding: 0.6rem;
            font-size: 1.2rem;
            text-align: right;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            margin-bottom: 0.75rem;
            background: #f8fafc;
            font-family: monospace;
            font-weight: bold;
        }

        .calc-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 0.35rem;
        }

        .calc-btn {
            padding: 0.55rem 0.2rem;
            font-size: 0.85rem;
            font-weight: 600;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            background: #fff;
            cursor: pointer;
        }

        .calc-btn:hover { background: #e2e8f0; }
        .calc-btn.op { background: #eff6ff; color: var(--primary-header); }
        .calc-btn.special { background: var(--skipped-bg); color: var(--accent-gold); }

        #desmos-calculator {
            width: 100%;
            height: 260px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }

        .results-summary {
            background: var(--card-bg); border-radius: 12px; padding: 2rem;
            border: 1px solid var(--border-color); margin-bottom: 2rem; text-align: center;
        }

        .score-circle {
            width: 130px; height: 130px; border-radius: 50%; background: var(--header-gradient);
            color: white; display: flex; flex-direction: column; align-items: center;
            justify-content: center; margin: 1rem auto;
        }

        .score-num { font-size: 2.2rem; font-weight: 800; color: var(--accent-gold-light); }
        .review-list { display: flex; flex-direction: column; gap: 1.5rem; }
        .review-card { background: var(--card-bg); border-radius: 12px; padding: 1.5rem; border: 1px solid var(--border-color); }

        .status-tag {
            padding: 0.25rem 0.6rem; border-radius: 4px; font-size: 0.75rem;
            font-weight: 700; text-transform: uppercase;
        }

        .tag-correct { background: var(--correct-bg); color: #065f46; }
        .tag-incorrect { background: var(--incorrect-bg); color: #991b1b; }
        .tag-skipped { background: var(--skipped-bg); color: #92400e; }

        @media (max-width: 992px) {
            .quiz-container { grid-template-columns: 1fr; }
            .quiz-sidebar { position: static; }
        }
    </style>
</head>
<body>

    <header>
        <div>
            <div class="brand-title">BRAIN AND MIND ACADEMY</div>
            <div class="brand-subtitle">Digital SAT Practice Test 5 Math • Interactive Micro-Learning Sheet</div>
        </div>
        <div class="user-info" id="user-header-info" style="display: none;">
            <span class="user-email" id="display-user-email"></span>
            <button class="btn btn-outline" style="color:white; border-color:rgba(255,255,255,0.3);" onclick="logout()">Switch User</button>
        </div>
    </header>

    <!-- Auth Screen -->
    <div id="auth-screen" class="screen active">
        <div class="auth-card">
            <h2>Digital SAT Portal</h2>
            <p>Enter your student email and choose your test module focus to begin.</p>
            <form onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label for="email-input">Email Address</label>
                    <input type="email" id="email-input" required placeholder="student@satprep.edu">
                </div>
                <div class="form-group">
                    <label for="module-select">Practice Scope</label>
                    <select id="module-select">
                        <option value="both">Full Test (Module 1 & Module 2 Cards)</option>
                        <option value="m1">Math: Module 1 Focus</option>
                        <option value="m2">Math: Module 2 Focus</option>
                    </select>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Start SAT Learning Cards</button>
            </form>
        </div>
    </div>

    <!-- Quiz Screen -->
    <div id="quiz-screen" class="screen">
        <div class="quiz-container">
            <div class="quiz-card">
                <div class="quiz-switch-bar">
                    <button class="switch-tab active-tab" id="tab-all" onclick="setQuizFilter('both')">All Questions</button>
                    <button class="switch-tab" id="tab-m1" onclick="setQuizFilter('m1')">Module 1</button>
                    <button class="switch-tab" id="tab-m2" onclick="setQuizFilter('m2')">Module 2</button>
                </div>

                <div class="quiz-header">
                    <span class="q-badge" id="q-number-badge">Card 1 of 18</span>
                    <span style="font-size: 0.85rem; color: var(--text-muted);" id="q-section-badge">Math Module 1</span>
                </div>

                <div class="q-title" id="q-title-text"></div>
                <div class="problem-statement" id="q-problem-text"></div>
                <div class="scale-graph-container" id="q-graph-container" style="display: none;"></div>

                <!-- STEP 1 BLOCK -->
                <div class="step-block active-step" id="step1-block">
                    <div class="step-header">
                        <span class="step-tag" id="step1-tag">Step 1: Conceptual Identification</span>
                        <span id="step1-status-tag" style="font-weight:700; font-size:0.8rem; color:var(--accent-gold);">In Progress</span>
                    </div>
                    <div class="step-prompt" id="step1-prompt"></div>
                    <div class="step-options-list" id="step1-options-container"></div>
                    <div class="step-actions" id="step1-actions">
                        <button class="btn btn-primary btn-sm" onclick="checkStep(1)">Check Step 1</button>
                        <button class="btn btn-gold btn-sm" onclick="skipStep(1)">Skip Step 1</button>
                    </div>
                </div>

                <!-- STEP 2 BLOCK -->
                <div class="step-block locked" id="step2-block">
                    <div class="step-header">
                        <span class="step-tag" id="step2-tag">Step 2: Algebraic Formulation</span>
                        <span id="step2-status-tag" style="font-weight:700; font-size:0.8rem; color:var(--text-muted);">Locked</span>
                    </div>
                    <div class="step-prompt" id="step2-prompt"></div>
                    <div class="step-options-list" id="step2-options-container"></div>
                    <div class="step-actions" id="step2-actions" style="display:none;">
                        <button class="btn btn-primary btn-sm" onclick="checkStep(2)">Check Step 2</button>
                        <button class="btn btn-gold btn-sm" onclick="skipStep(2)">Skip Step 2</button>
                    </div>
                </div>

                <!-- STEP 3 BLOCK -->
                <div class="step-block locked" id="step3-block">
                    <div class="step-header">
                        <span class="step-tag" id="step3-tag">Step 3: Final Answer & Verification</span>
                        <span id="step3-status-tag" style="font-weight:700; font-size:0.8rem; color:var(--text-muted);">Locked</span>
                    </div>
                    <div class="step-prompt" id="step3-prompt"></div>
                    <div class="step-options-list" id="step3-options-container"></div>
                    <div class="step-actions" id="step3-actions" style="display:none;">
                        <button class="btn btn-primary btn-sm" onclick="checkStep(3)">Check Step 3</button>
                        <button class="btn btn-gold btn-sm" onclick="skipStep(3)">Skip Step 3</button>
                    </div>
                </div>

                <div class="action-bar">
                    <button class="btn btn-danger" id="skip-card-btn" onclick="skipEntireCard()">Skip Entire Card</button>
                    <button class="btn btn-outline" id="next-btn" style="display: none;" onclick="nextQuestion()">Next Card &rarr;</button>
                </div>

                <div class="rationale-box" id="rationale-container" style="display: none;">
                    <div class="rationale-title">Full Step-by-Step SAT Solution & College Board Rationale</div>
                    <div id="rationale-text" style="font-size: 0.95rem; line-height: 1.6;"></div>
                </div>
            </div>

            <!-- Sidebar -->
            <div class="quiz-sidebar">
                <div class="sidebar-card">
                    <div class="sidebar-title">Question Navigator</div>
                    <div class="legend-grid">
                        <div class="legend-item"><div class="legend-dot dot-active"></div> Active</div>
                        <div class="legend-item"><div class="legend-dot dot-attempted"></div> Submitted</div>
                        <div class="legend-item"><div class="legend-dot dot-skipped"></div> Skipped</div>
                        <div class="legend-item"><div class="legend-dot dot-unvisited"></div> Unvisited</div>
                    </div>
                    <div class="question-grid" id="question-grid"></div>
                    <div style="margin-top: 1rem;">
                        <button class="btn btn-danger" style="width: 100%;" onclick="finishTest()">Finish & Review Module</button>
                    </div>
                </div>

                <!-- Desmos Graphing Calculator Embed -->
                <div class="sidebar-card">
                    <div class="sidebar-title" style="margin-bottom:0.5rem;">Desmos SAT Graphing Calculator</div>
                    <div id="desmos-calculator"></div>
                </div>

                <!-- Scientific Calculator -->
                <div class="sidebar-card">
                    <div class="sidebar-title" style="margin-bottom:0.5rem;">Scientific Calculator</div>
                    <input type="text" class="calc-display" id="calc-disp" readonly value="0">
                    <div class="calc-grid">
                        <button class="calc-btn special" onclick="calcSqrt()">√x</button>
                        <button class="calc-btn special" onclick="calcInput('**2')">x²</button>
                        <button class="calc-btn special" onclick="calcInput('**3')">x³</button>
                        <button class="calc-btn op" onclick="calcClear()">C</button>

                        <button class="calc-btn" onclick="calcInput('7')">7</button>
                        <button class="calc-btn" onclick="calcInput('8')">8</button>
                        <button class="calc-btn" onclick="calcInput('9')">9</button>
                        <button class="calc-btn op" onclick="calcInput('/')">÷</button>
                        
                        <button class="calc-btn" onclick="calcInput('4')">4</button>
                        <button class="calc-btn" onclick="calcInput('5')">5</button>
                        <button class="calc-btn" onclick="calcInput('6')">6</button>
                        <button class="calc-btn op" onclick="calcInput('*')">×</button>
                        
                        <button class="calc-btn" onclick="calcInput('1')">1</button>
                        <button class="calc-btn" onclick="calcInput('2')">2</button>
                        <button class="calc-btn" onclick="calcInput('3')">3</button>
                        <button class="calc-btn op" onclick="calcInput('-')">-</button>
                        
                        <button class="calc-btn" onclick="calcInput('0')">0</button>
                        <button class="calc-btn" onclick="calcInput('.')">.</button>
                        <button class="calc-btn op" onclick="calcInput('+')">+</button>
                        <button class="calc-btn op" onclick="calcEval()">=</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Review Screen -->
    <div id="review-screen" class="screen">
        <div class="results-summary">
            <h2>Digital SAT Practice Test 5 Math Report</h2>
            <div class="score-circle">
                <span class="score-num" id="final-score">0 / 18</span>
                <span style="font-size: 0.8rem; opacity: 0.8;">Raw Score</span>
            </div>
            <button class="btn btn-primary" onclick="restartQuiz()">Retake Assessment</button>
        </div>

        <h3 style="margin-bottom: 1rem; color: var(--primary-header);">Student Performance & Solution Review</h3>
        <div class="review-list" id="review-list"></div>
    </div>

    <script>
        const AudioFX = {
            ctx: null,
            init() {
                if (!this.ctx) {
                    this.ctx = new (window.AudioContext || window.webkitAudioContext)();
                }
                if (this.ctx.state === 'suspended') {
                    this.ctx.resume();
                }
            },
            playCorrectBell() {
                this.init();
                const now = this.ctx.currentTime;
                const playSingleBell = (freq, time, duration) => {
                    const osc = this.ctx.createOscillator();
                    const gain = this.ctx.createGain();

                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(freq, time);

                    gain.gain.setValueAtTime(0, time);
                    gain.gain.linearRampToValueAtTime(0.3, time + 0.01);
                    gain.gain.exponentialRampToValueAtTime(0.001, time + duration);

                    osc.connect(gain);
                    gain.connect(this.ctx.destination);

                    osc.start(time);
                    osc.stop(time + duration);
                };

                playSingleBell(880, now, 0.8);        
                playSingleBell(1318.51, now + 0.12, 1.2); 
            },
            playIncorrectBell() {
                this.init();
                const now = this.ctx.currentTime;

                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();

                osc.type = 'triangle';
                osc.frequency.setValueAtTime(220, now); 

                gain.gain.setValueAtTime(0, now);
                gain.gain.linearRampToValueAtTime(0.35, now + 0.01);
                gain.gain.exponentialRampToValueAtTime(0.001, now + 0.6);

                osc.connect(gain);
                gain.connect(this.ctx.destination);

                osc.start(now);
                osc.stop(now + 0.6);
            },
            playSkipChime() {
                this.init();
                const now = this.ctx.currentTime;

                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();

                osc.type = 'sine';
                osc.frequency.setValueAtTime(523.25, now); 
                osc.frequency.exponentialRampToValueAtTime(392, now + 0.15); 

                gain.gain.setValueAtTime(0.15, now);
                gain.gain.exponentialRampToValueAtTime(0.001, now + 0.15);

                osc.connect(gain);
                gain.connect(this.ctx.destination);

                osc.start(now);
                osc.stop(now + 0.15);
            }
        };

        const CHAPTER_KEY = "SAT_PRACTICE_TEST_5_DIGITAL_MATH_CARDS";

        // Accurate SVG Coordinate Grid Scale Generator
        function generateSATGridSVG(elements, xRange = [-2, 8], yRange = [-3, 8], width = 300, height = 260) {
            const pad = 30;
            const plotW = width - 2 * pad;
            const plotH = height - 2 * pad;
            
            const toX = val => pad + ((val - xRange[0]) / (xRange[1] - xRange[0])) * plotW;
            const toY = val => pad + ((yRange[1] - val) / (yRange[1] - yRange[0])) * plotH;

            let gridLines = '';
            for (let x = Math.ceil(xRange[0]); x <= Math.floor(xRange[1]); x++) {
                gridLines += `<line x1="${toX(x)}" y1="${pad}" x2="${toX(x)}" y2="${height - pad}" stroke="#e2e8f0" stroke-width="1"/>`;
                if (x !== 0) {
                    gridLines += `<text x="${toX(x)}" y="${toY(0) + 14}" font-size="9" text-anchor="middle" fill="#64748b">${x}</text>`;
                }
            }
            for (let y = Math.ceil(yRange[0]); y <= Math.floor(yRange[1]); y++) {
                gridLines += `<line x1="${pad}" y1="${toY(y)}" x2="${width - pad}" y2="${toY(y)}" stroke="#e2e8f0" stroke-width="1"/>`;
                if (y !== 0) {
                    gridLines += `<text x="${toX(0) - 7}" y="${toY(y) + 3}" font-size="9" text-anchor="end" fill="#64748b">${y}</text>`;
                }
            }

            const xAxis = `<line x1="${pad - 12}" y1="${toY(0)}" x2="${width - pad + 12}" y2="${toY(0)}" stroke="#334155" stroke-width="2"/>
                           <text x="${width - pad + 16}" y="${toY(0) + 4}" font-size="11" font-weight="bold" fill="#334155">x</text>`;
            const yAxis = `<line x1="${toX(0)}" y1="${height - pad + 12}" x2="${toX(0)}" y2="${pad - 12}" stroke="#334155" stroke-width="2"/>
                           <text x="${toX(0) + 5}" y="${pad - 14}" font-size="11" font-weight="bold" fill="#334155">y</text>`;

            let content = '';
            elements.forEach(el => {
                if (el.type === 'curve') {
                    let d = '';
                    const step = 0.05;
                    let first = true;
                    for (let x = el.min; x <= el.max; x += step) {
                        const y = el.fn(x);
                        if (y >= yRange[0] - 1 && y <= yRange[1] + 1) {
                            d += `${first ? 'M' : 'L'} ${toX(x).toFixed(1)} ${toY(y).toFixed(1)} `;
                            first = false;
                        } else {
                            first = true;
                        }
                    }
                    content += `<path d="${d}" fill="none" stroke="${el.color}" stroke-width="${el.width || 2.5}"/>`;
                } else if (el.type === 'point') {
                    content += `<circle cx="${toX(el.x)}" cy="${toY(el.y)}" r="${el.r || 4}" fill="${el.color}"/>`;
                    if (el.label) {
                        content += `<text x="${toX(el.x) + 7}" y="${toY(el.y) - 6}" font-size="10" font-weight="bold" fill="${el.color}">${el.label}</text>`;
                    }
                } else if (el.type === 'line') {
                    content += `<line x1="${toX(el.x1)}" y1="${toY(el.y1)}" x2="${toX(el.x2)}" y2="${toY(el.y2)}" stroke="${el.color}" stroke-width="${el.width || 2.5}"/>`;
                }
            });

            return `<svg width="${width}" height="${height}" viewBox="0 0 ${width} ${height}">${gridLines}${xAxis}${yAxis}${content}</svg>`;
        }

        // SVG Diagram for Parallel Lines and Transversal
        function generateTransversalSVG() {
            return `<svg width="280" height="150" viewBox="0 0 280 150">
                <line x1="20" y1="40" x2="260" y2="40" stroke="#1e3a8a" stroke-width="2.5"/>
                <text x="265" y="44" font-weight="bold" fill="#1e3a8a">m</text>
                <line x1="20" y1="110" x2="260" y2="110" stroke="#1e3a8a" stroke-width="2.5"/>
                <text x="265" y="114" font-weight="bold" fill="#1e3a8a">n</text>
                <line x1="70" y1="15" x2="210" y2="135" stroke="#d97706" stroke-width="2.5"/>
                <text x="215" y="140" font-weight="bold" fill="#d97706">k</text>
                <path d="M 175 110 A 25 25 0 0 0 162 93" fill="none" stroke="#dc2626" stroke-width="2"/>
                <text x="180" y="98" font-size="11" font-weight="bold" fill="#dc2626">145°</text>
                <path d="M 152 110 A 25 25 0 0 1 162 93" fill="none" stroke="#059669" stroke-width="2"/>
                <text x="134" y="98" font-size="11" font-weight="bold" fill="#059669">x°</text>
            </svg>`;
        }

        // SVG Diagram for Right Triangle ABC
        function generateRightTriangleSVG() {
            return `<svg width="260" height="140" viewBox="0 0 260 140">
                <polygon points="40,110 220,110 40,25" fill="#f8fafc" stroke="#1e3a8a" stroke-width="2.5"/>
                <rect x="40" y="95" width="15" height="15" fill="none" stroke="#334155" stroke-width="1.5"/>
                <text x="35" y="125" font-size="11" font-weight="bold">B</text>
                <text x="225" y="120" font-size="11" font-weight="bold">A</text>
                <text x="35" y="20" font-size="11" font-weight="bold">C</text>
                <text x="120" y="128" font-size="11" font-weight="bold" fill="#1e3a8a">11</text>
                <text x="140" y="60" font-size="11" font-weight="bold" fill="#d97706">28</text>
                <path d="M 195 110 A 25 25 0 0 1 185 96" fill="none" stroke="#059669" stroke-width="2"/>
                <text x="175" y="102" font-size="10" font-weight="bold" fill="#059669">θ</text>
            </svg>`;
        }

        // SVG Diagram for Cylinder
        function generateCylinderSVG() {
            return `<svg width="220" height="150" viewBox="0 0 220 150">
                <ellipse cx="110" cy="35" rx="65" ry="18" fill="#e0e7ff" stroke="#1e3a8a" stroke-width="2.5"/>
                <line x1="45" y1="35" x2="45" y2="105" stroke="#1e3a8a" stroke-width="2.5"/>
                <line x1="175" y1="35" x2="175" y2="105" stroke="#1e3a8a" stroke-width="2.5"/>
                <path d="M 45 105 A 65 18 0 0 0 175 105" fill="#e0e7ff" stroke="#1e3a8a" stroke-width="2.5"/>
                <line x1="45" y1="35" x2="175" y2="35" stroke="#dc2626" stroke-width="1.5" stroke-dasharray="3"/>
                <text x="90" y="28" font-size="10" font-weight="bold" fill="#dc2626">d = 22 cm</text>
                <line x1="185" y1="35" x2="185" y2="105" stroke="#334155" stroke-width="1.5"/>
                <text x="192" y="75" font-size="11" font-weight="bold" fill="#334155">h = 6 cm</text>
            </svg>`;
        }

        // Complete 18 Core Digital SAT Practice Test 5 Math Questions (Module 1 & Module 2)
        const questionsData = [
            // Card 1: Module 1, Q1
            {
                id: 1,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'y=-x+5',
                title: "Card 1 (Module 1, Question 1): System of Linear and Nonlinear Equations",
                problem: "The graph of a system of a linear equation and a nonlinear equation is shown in the xy-plane. What is the solution (x, y) to this system?",
                graphSVG: generateSATGridSVG([
                    { type: 'line', x1: -1, y1: 6, x2: 6, y2: -1, color: '#1e3a8a', width: 2.5 },
                    { type: 'curve', fn: x => 4 * Math.pow(1 - x/5, 2), min: -1, max: 6, color: '#d97706', width: 2.5 },
                    { type: 'point', x: 5, y: 0, color: '#dc2626', r: 5, label: '(5, 0)' }
                ], [-1, 7], [-2, 7]),
                step1: {
                    tag: "Step 1: Graphical Solution Definition",
                    prompt: "What represents the solution (x, y) to a system of equations graphed in the xy-plane?",
                    options: [
                        "The distance between the two graphs along the y-axis.",
                        "The point or points of intersection where the graphs meet and satisfy both equations simultaneously.",
                        "The highest peak on the nonlinear graph.",
                        "The origin coordinate (0, 0)."
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Coordinate Identification",
                    prompt: "Read the coordinates where the line and curve intersect on the x-axis from the scale grid:",
                    options: [
                        "Point of intersection is (0, 4)",
                        "Point of intersection is (0, 5)",
                        "Point of intersection is (5, 0)",
                        "Point of intersection is (4, 5)"
                    ],
                    correct: 2 // Option C
                },
                step3: {
                    tag: "Step 3: State the Solution",
                    prompt: "Select the correct solution ordered pair (x, y):",
                    options: [
                        "(x, y) = (5, 0)",
                        "(x, y) = (0, 0)",
                        "(x, y) = (0, 4)",
                        "(x, y) = (4, 5)"
                    ],
                    correct: 0 // Option A
                },
                rationale: "The solution to a system of equations shown as a graph is the coordinate point of intersection. Inspecting the graph, the line and nonlinear curve cross exactly on the x-axis at x = 5 and y = 0. Therefore, the solution is (5, 0)."
            },
            // Card 2: Module 1, Q2
            {
                id: 2,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'M(d)=90+10d',
                title: "Card 2 (Module 1, Question 2): Linear Growth / Sequence",
                problem: "On the first day of the semester, 90 members joined the film club. Each day after the first day of the semester, 10 new members join the film club. If no members leave the film club, how many total members will the film club have 4 days after the first day of the semester?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Model Formulation",
                    prompt: "Formulate a linear model for the total members M as a function of days elapsed d after the first day:",
                    options: [
                        "Total members M(d) = 90 × (10)^d",
                        "Total members M(d) = 90 + 10 × d",
                        "Total members M(d) = 90d + 10",
                        "Total members M(d) = 90 - 10 × d"
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Substitution for d = 4",
                    prompt: "Substitute d = 4 into the linear growth model: M(4) = 90 + 10(4):",
                    options: [
                        "M(4) = 90 + 40",
                        "M(4) = 90 × 40",
                        "M(4) = 360 + 10",
                        "M(4) = 90 + 14"
                    ],
                    correct: 0 // Option A
                },
                step3: {
                    tag: "Step 3: Final Computation",
                    prompt: "Calculate the total number of members: 90 + 40 = [ _____ ]:",
                    options: [
                        "Total members = 100",
                        "Total members = 140",
                        "Total members = 120",
                        "Total members = 130"
                    ],
                    correct: 3 // Option D
                },
                rationale: "On day 0 (first day), there are 90 members. For each of the 4 days, 10 new members join: 4 × 10 = 40 new members. Total members = 90 + 40 = 130."
            },
            // Card 3: Module 1, Q3
            {
                id: 3,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'y=-(16/11)x+8',
                title: "Card 3 (Module 1, Question 3): Finding y-Intercept from a Graph",
                problem: "The graph of a linear function is shown in the xy-plane. What is the y-intercept of the line?",
                graphSVG: generateSATGridSVG([
                    { type: 'line', x1: -2, y1: 10.9, x2: 8, y2: -3.6, color: '#1e3a8a', width: 2.5 },
                    { type: 'point', x: 0, y: 8, color: '#dc2626', r: 5, label: '(0, 8)' }
                ], [-3, 9], [-4, 11]),
                step1: {
                    tag: "Step 1: Definition of y-Intercept",
                    prompt: "What is the defining geometric and algebraic characteristic of a y-intercept?",
                    options: [
                        "The point where the line crosses the horizontal x-axis (y = 0).",
                        "The slope of the line.",
                        "The point where the line crosses the vertical y-axis, where the x-coordinate equals 0.",
                        "The midpoint of the line segment."
                    ],
                    correct: 2 // Option C
                },
                step2: {
                    tag: "Step 2: Read Value from Scale Axis",
                    prompt: "Observe the y-axis in the scale grid. At what y-value does the line intersect the vertical axis?",
                    options: [
                        "The line crosses the vertical axis at y = 8.",
                        "The line crosses the vertical axis at y = 0.",
                        "The line crosses the vertical axis at y = -8.",
                        "The line crosses the vertical axis at y = -16/11."
                    ],
                    correct: 0 // Option A
                },
                step3: {
                    tag: "Step 3: Express as an Ordered Pair",
                    prompt: "Select the correct coordinates of the y-intercept:",
                    options: [
                        "y-intercept = (8, 0)",
                        "y-intercept = (0, 8)",
                        "y-intercept = (0, 0)",
                        "y-intercept = (0, -8)"
                    ],
                    correct: 1 // Option B
                },
                rationale: "The y-intercept is the point on the coordinate plane where the graph intersects the y-axis (x = 0). As visible on the graph, the line crosses the y-axis at y = 8. Hence, the y-intercept is (0, 8)."
            },
            // Card 4: Module 1, Q4
            {
                id: 4,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 's+7r=27',
                title: "Card 4 (Module 1, Question 4): Linear System by Substitution",
                problem: "Consider the system of linear equations: s + 7r = 27 and r = 3. What is the solution (r, s) to this system?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Choose Substitution Strategy",
                    prompt: "Given that the second equation explicitly provides r = 3, what is the fastest solving strategy?",
                    options: [
                        "Graph both lines on paper.",
                        "Substitute r = 3 directly into the first equation to solve for s.",
                        "Multiply the second equation by 7.",
                        "Divide the first equation by 27."
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Substitute and Simplify",
                    prompt: "Substitute r = 3 into s + 7r = 27: s + 7(3) = 27:",
                    options: [
                        "s + 21 = 27",
                        "s + 10 = 27",
                        "s + 7 = 27",
                        "s = 27 × 21"
                    ],
                    correct: 0 // Option A
                },
                step3: {
                    tag: "Step 3: Solve for s and Form Solution Pair",
                    prompt: "Subtract 21 from 27: s = 6. State the solution pair (r, s):",
                    options: [
                        "Solution (r, s) = (6, 3)",
                        "Solution (r, s) = (3, 27)",
                        "Solution (r, s) = (3, 6)",
                        "Solution (r, s) = (27, 3)"
                    ],
                    correct: 2 // Option C
                },
                rationale: "Substitute r = 3 into s + 7r = 27: s + 7(3) = 27 ⇒ s + 21 = 27 ⇒ s = 6. The question asks for the ordered pair (r, s), which is (3, 6)."
            },
            // Card 5: Module 1, Q5
            {
                id: 5,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'f(x)=x+16',
                title: "Card 5 (Module 1, Question 5): Linear vs. Exponential Function Modeling",
                problem: "The table shows values of x and corresponding values of f(x): (0, 16), (1, 17), (2, 18), and (3, 19). Which model best describes the relationship?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Rate of Change Analysis",
                    prompt: "Compute the consecutive differences Δf(x) for equal increments of Δx = 1:",
                    options: [
                        "The ratios are constant: 17/16 = 18/17",
                        "The differences are constant: 17 - 16 = 1, 18 - 17 = 1, 19 - 18 = 1",
                        "The values are decreasing.",
                        "The differences are doubling."
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Distinguish Model Type",
                    prompt: "A constant first difference indicates which type of mathematical function?",
                    options: [
                        "Exponential function",
                        "Quadratic function",
                        "Linear function",
                        "Rational function"
                    ],
                    correct: 2 // Option C
                },
                step3: {
                    tag: "Step 3: Determine Direction and Conclusion",
                    prompt: "Since the constant difference is positive (+1), what is the best description?",
                    options: [
                        "Decreasing linear function",
                        "Increasing exponential function",
                        "Decreasing exponential function",
                        "Increasing linear function"
                    ],
                    correct: 3 // Option D
                },
                rationale: "Because f(x) increases by equal amounts (+1) over equal intervals of x (+1), the rate of change is constant. A constant positive rate of change defines an increasing linear function."
            },
            // Card 6: Module 1, Q6
            {
                id: 6,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'y=0.5x-3',
                title: "Card 6 (Module 1, Question 6): System Solution from Intersection Point",
                problem: "The graph of a system of two linear equations is shown. The lines intersect at (x, y). What is the value of x?",
                graphSVG: generateSATGridSVG([
                    { type: 'line', x1: -2, y1: -4, x2: 7, y2: 0.5, color: '#1e3a8a', width: 2.5 },
                    { type: 'line', x1: 1, y1: 5, x2: 6, y2: -5, color: '#059669', width: 2.5 },
                    { type: 'point', x: 4, y: -1, color: '#dc2626', r: 5, label: '(4, -1)' }
                ], [-2, 8], [-5, 6]),
                step1: {
                    tag: "Step 1: Identify Intersection Principle",
                    prompt: "How is the solution to a graphed system of linear equations determined?",
                    options: [
                        "By measuring the angle between the lines.",
                        "By reading the coordinate point (x, y) where the two lines intersect.",
                        "By averaging the x-intercepts.",
                        "By adding the slopes of the two lines."
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Read Grid Coordinates",
                    prompt: "Locate the intersection point on the scale coordinate grid:",
                    options: [
                        "The intersection point is (4, -1)",
                        "The intersection point is (-1, 4)",
                        "The intersection point is (0, -3)",
                        "The intersection point is (2, -2)"
                    ],
                    correct: 0 // Option A
                },
                step3: {
                    tag: "Step 3: Extract the Value of x",
                    prompt: "From the intersection coordinate (4, -1), state the value of x:",
                    options: [
                        "x = -1",
                        "x = 3",
                        "x = 4",
                        "x = 5"
                    ],
                    correct: 2 // Option C
                },
                rationale: "The intersection of the two lines on the grid is at x = 4 and y = -1. Since the question asks specifically for the value of x, the answer is 4."
            },
            // Card 7: Module 1, Q7
            {
                id: 7,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'L=[23, 27, 27, 32, 35, 36, 52]',
                title: "Card 7 (Module 1, Question 7): Range of a Dataset",
                problem: "The test scores of 7 students are 23, 27, 27, 32, 35, 36, 52. What is the range of the 7 scores shown?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Range Formula Definition",
                    prompt: "What is the formula used in statistics to calculate the range of a dataset?",
                    options: [
                        "Range = Sum of all values / Number of values",
                        "Range = Maximum value - Minimum value",
                        "Range = Middle score (Median)",
                        "Range = Third quartile - First quartile"
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Identify Extreme Values",
                    prompt: "Identify the minimum and maximum values in the given sorted dataset:",
                    options: [
                        "Minimum = 27, Maximum = 52",
                        "Minimum = 23, Maximum = 36",
                        "Minimum = 23, Maximum = 52",
                        "Minimum = 0, Maximum = 100"
                    ],
                    correct: 2 // Option C
                },
                step3: {
                    tag: "Step 3: Calculate the Range",
                    prompt: "Subtract: 52 - 23 = [ _____ ]:",
                    options: [
                        "Range = 29",
                        "Range = 32",
                        "Range = 25",
                        "Range = 27"
                    ],
                    correct: 0 // Option A
                },
                rationale: "Range measures the spread between the maximum and minimum values in a dataset: Range = Max - Min = 52 - 23 = 29."
            },
            // Card 8: Module 1, Q8
            {
                id: 8,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'x+145=180',
                title: "Card 8 (Module 1, Question 8): Parallel Lines and Transversal Angles",
                problem: "Lines m and n are parallel and cut by transversal k. An angle of measure 145° and an adjacent angle of measure x° lie along line n on the same side of the transversal. Which statement must be true?",
                graphSVG: generateTransversalSVG(),
                step1: {
                    tag: "Step 1: Geometric Angle Relationship",
                    prompt: "What geometric relationship exists between the adjacent angles 145° and x° forming a straight line on line n?",
                    options: [
                        "They are vertical angles and therefore equal.",
                        "They form a linear pair on a straight line and are supplementary (their sum is 180°).",
                        "They are complementary and sum to 90°.",
                        "They are alternate interior angles."
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Calculate x",
                    prompt: "Solve the linear equation: x + 145 = 180:",
                    options: [
                        "x = 180 - 145 = 35°",
                        "x = 145°",
                        "x = 90 - 45 = 45°",
                        "x = 55°"
                    ],
                    correct: 0 // Option A
                },
                step3: {
                    tag: "Step 3: Evaluate Statement",
                    prompt: "Compare x = 35° with 145°:",
                    options: [
                        "The value of x is equal to 145.",
                        "The value of x is greater than 145.",
                        "The value of x is less than 145.",
                        "The value of x cannot be determined."
                    ],
                    correct: 2 // Option C
                },
                rationale: "Angles that form a linear pair along a straight line sum to 180°: x + 145 = 180 ⇒ x = 35. Since 35 < 145, the true statement is that the value of x is less than 145."
            },
            // Card 9: Module 1, Q11
            {
                id: 9,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: '4x-28=-24',
                title: "Card 9 (Module 1, Question 11): Linear Equation in One Variable",
                problem: "If 4x - 28 = -24, what is the value of x - 7?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Structural Relationship Recognition",
                    prompt: "Notice the algebraic relationship between 4x - 28 and the target expression x - 7:",
                    options: [
                        "Multiply 4x - 28 by 4.",
                        "Divide both sides of the equation 4x - 28 = -24 by 4 directly: (4x - 28)/4 = x - 7.",
                        "Square both sides.",
                        "Add 28 to both sides and stop."
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Execute Division",
                    prompt: "Divide -24 by 4: (x - 7) = -24 / 4:",
                    options: [
                        "x - 7 = 6",
                        "x - 7 = -1",
                        "x - 7 = -6",
                        "x - 7 = -24"
                    ],
                    correct: 2 // Option C
                },
                step3: {
                    tag: "Step 3: Verification via Solving for x",
                    prompt: "Alternatively, solve 4x = -24 + 28 = 4 ⇒ x = 1. Then compute x - 7 = 1 - 7 = [ _____ ]:",
                    options: [
                        "x - 7 = -6",
                        "x - 7 = 6",
                        "x - 7 = -8",
                        "x - 7 = 0"
                    ],
                    correct: 0 // Option A
                },
                rationale: "Dividing the entire equation 4x - 28 = -24 by 4 gives x - 7 = -6 directly. Alternatively, 4x = 4 ⇒ x = 1, so x - 7 = 1 - 7 = -6."
            },
            // Card 10: Module 1, Q13
            {
                id: 10,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'x^2-4x-12=0',
                title: "Card 10 (Module 1, Question 13): Nonlinear System of Equations",
                problem: "A solution to the given system of equations y = 4x and y = x^2 - 12 is (x, y), where x > 0. What is the value of x?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Equate Expressions for y",
                    prompt: "Set the two expressions for y equal to one another to create a single quadratic equation:",
                    options: [
                        "x^2 - 12 = 4x",
                        "x^2 + 4x = 12",
                        "4x(x^2 - 12) = 0",
                        "x^2 = 4x + 12"
                    ],
                    correct: 0 // Option A
                },
                step2: {
                    tag: "Step 2: Standard Quadratic Form & Factoring",
                    prompt: "Rearrange to standard form x^2 - 4x - 12 = 0 and factor:",
                    options: [
                        "(x - 4)(x + 3) = 0",
                        "(x - 12)(x + 1) = 0",
                        "(x - 6)(x + 2) = 0",
                        "(x + 6)(x - 2) = 0"
                    ],
                    correct: 2 // Option C
                },
                step3: {
                    tag: "Step 3: Select Positive Root",
                    prompt: "The roots are x = 6 and x = -2. Applying the constraint x > 0, state x:",
                    options: [
                        "x = -2",
                        "x = 6",
                        "x = 12",
                        "x = 4"
                    ],
                    correct: 1 // Option B
                },
                rationale: "Equating gives x^2 - 4x - 12 = 0. Factoring gives (x - 6)(x + 2) = 0, yielding x = 6 or x = -2. The problem specifies x > 0, so x = 6."
            },
            // Card 11: Module 1, Q15
            {
                id: 11,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: 'V=\\pi(11)^2(6)',
                title: "Card 11 (Module 1, Question 15): Volume of a Right Circular Cylinder",
                problem: "A right circular cylinder has a base diameter of 22 centimeters and a height of 6 centimeters. What is the volume, in cubic centimeters, of the cylinder?",
                graphSVG: generateCylinderSVG(),
                step1: {
                    tag: "Step 1: Base Radius Determination",
                    prompt: "Find the base radius r from the given diameter of 22 cm:",
                    options: [
                        "Radius r = 22 cm",
                        "Radius r = 22 / 2 = 11 cm",
                        "Radius r = √22 cm",
                        "Radius r = 44 cm"
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Cylinder Volume Formula",
                    prompt: "State the formula for the volume of a right circular cylinder:",
                    options: [
                        "Volume = 2πrh",
                        "Volume = (1/3)πr^2 h",
                        "Volume = πr^2 h",
                        "Volume = (4/3)πr^3"
                    ],
                    correct: 2 // Option C
                },
                step3: {
                    tag: "Step 3: Substitute and Calculate",
                    prompt: "Substitute r = 11 and h = 6 into V = π(11)^2(6):",
                    options: [
                        "Volume = 726π cm^3",
                        "Volume = 132π cm^3",
                        "Volume = 2904π cm^3",
                        "Volume = 66π cm^3"
                    ],
                    correct: 0 // Option A
                },
                rationale: "Radius r = diameter / 2 = 11 cm. Volume = πr^2 h = π(11)^2 (6) = π(121)(6) = 726π cm^3."
            },
            // Card 12: Module 1, Q19
            {
                id: 12,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: '\\tan(92\\pi/3)',
                title: "Card 12 (Module 1, Question 19): Trigonometric Value on the Unit Circle",
                problem: "What is the value of tan(92π / 3)?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Periodicity of Tangent",
                    prompt: "Recall that tan(θ) has a fundamental period of π radians. Reduce 92π / 3 modulo π:",
                    options: [
                        "92π / 3 = 30π + 2π/3, so tan(92π/3) = tan(2π/3)",
                        "92π / 3 = 2π/3 + 4π",
                        "tan(92π/3) is undefined",
                        "tan(92π/3) = tan(π/3)"
                    ],
                    correct: 0 // Option A
                },
                step2: {
                    tag: "Step 2: Reference Angle and Quadrant",
                    prompt: "Determine the reference angle and sign for 2π/3 in Quadrant II:",
                    options: [
                        "Quadrant I: positive",
                        "Quadrant II: tan is negative, reference angle is π/3",
                        "Quadrant III: positive",
                        "Quadrant IV: negative, reference angle is π/6"
                    ],
                    correct: 1 // Option B
                },
                step3: {
                    tag: "Step 3: Calculate Exact Value",
                    prompt: "Evaluate -tan(π/3):",
                    options: [
                        "√3",
                        "-1 / √3",
                        "1",
                        "-√3"
                    ],
                    correct: 3 // Option D
                },
                rationale: "92/3 = 30 + 2/3. Since tan(θ) has period π, tan(92π/3) = tan(30π + 2π/3) = tan(2π/3). In Quadrant II, tan(2π/3) = -tan(π/3) = -√3."
            },
            // Card 13: Module 1, Q20
            {
                id: 13,
                module: 'm1',
                sectionName: 'Math: Module 1',
                desmosLatex: '\\cos(A)=11/28',
                title: "Card 13 (Module 1, Question 20): Right-Triangle Trigonometry Ratio",
                problem: "In right triangle ABC, angle B is a right angle. The side adjacent to angle A has length 11, and the hypotenuse has length 28. What is the value of cos(A)?",
                graphSVG: generateRightTriangleSVG(),
                step1: {
                    tag: "Step 1: Cosine Definition",
                    prompt: "State the trigonometric definition of cosine in a right triangle:",
                    options: [
                        "cos(A) = Opposite side / Hypotenuse",
                        "cos(A) = Opposite side / Adjacent side",
                        "cos(A) = Adjacent side / Hypotenuse",
                        "cos(A) = Hypotenuse / Adjacent side"
                    ],
                    correct: 2 // Option C
                },
                step2: {
                    tag: "Step 2: Substitute Triangle Sides",
                    prompt: "Substitute the side adjacent to angle A (11) and hypotenuse (28):",
                    options: [
                        "cos(A) = 11 / 28",
                        "cos(A) = 28 / 11",
                        "cos(A) = 11 / √(28^2 - 11^2)",
                        "cos(A) = √(28^2 - 11^2) / 28"
                    ],
                    correct: 0 // Option A
                },
                step3: {
                    tag: "Step 3: Final Fraction / Decimal Value",
                    prompt: "Select the exact value of cos(A):",
                    options: [
                        "28 / 11",
                        "11 / 28 (or approx 0.3929)",
                        "17 / 28",
                        "11 / 17"
                    ],
                    correct: 1 // Option B
                },
                rationale: "By SOH CAH TOA, cos(A) = Adjacent / Hypotenuse. The side adjacent to angle A is 11, and the hypotenuse is 28. Thus, cos(A) = 11/28."
            },
            // Card 14: Module 2, Q1
            {
                id: 14,
                module: 'm2',
                sectionName: 'Math: Module 2',
                desmosLatex: '0.20*440',
                title: "Card 14 (Module 2, Question 1): Percentage of a Number",
                problem: "What is 20% of 440?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Convert Percentage to Decimal",
                    prompt: "Convert 20% into an equivalent decimal multiplier:",
                    options: [
                        "20% = 2.0",
                        "20% = 0.20 = 1/5",
                        "20% = 0.02",
                        "20% = 20"
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Multiplication Setup",
                    prompt: "Set up the multiplication of 0.20 and 440:",
                    options: [
                        "440 / 0.20",
                        "440 + 20",
                        "0.20 × 440",
                        "440 - 20"
                    ],
                    correct: 2 // Option C
                },
                step3: {
                    tag: "Step 3: Final Product Calculation",
                    prompt: "Calculate 0.20 × 440 = 440 / 5 = [ _____ ]:",
                    options: [
                        "88",
                        "44",
                        "880",
                        "1760"
                    ],
                    correct: 0 // Option A
                },
                rationale: "20% of 440 = (20/100) × 440 = 0.20 × 440 = 88."
            },
            // Card 15: Module 2, Q6
            {
                id: 15,
                module: 'm2',
                sectionName: 'Math: Module 2',
                desmosLatex: '6n-3=45',
                title: "Card 15 (Module 2, Question 6): Linear Equation Scaling",
                problem: "If 6n - 3 = 45, what is the value of 2n?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Isolate 6n",
                    prompt: "Add 3 to both sides of the equation 6n - 3 = 45:",
                    options: [
                        "6n = 45 - 3 = 42",
                        "6n = 45 + 3 = 48",
                        "6n = 45 / 3 = 15",
                        "6n = 135"
                    ],
                    correct: 1 // Option B
                },
                step2: {
                    tag: "Step 2: Relate 6n to 2n",
                    prompt: "Notice that 2n is exactly 6n divided by 3:",
                    options: [
                        "2n = 6n / 3 = 48 / 3",
                        "2n = 6n × 3",
                        "2n = 6n - 4",
                        "2n = 48 / 2"
                    ],
                    correct: 0 // Option A
                },
                step3: {
                    tag: "Step 3: Calculate 2n",
                    prompt: "Evaluate 48 / 3 = [ _____ ]:",
                    options: [
                        "2n = 8",
                        "2n = 24",
                        "2n = 16",
                        "2n = 12"
                    ],
                    correct: 2 // Option C
                },
                rationale: "6n - 3 = 45 ⇒ 6n = 48. Dividing both sides by 3 gives 2n = 16. (Or n = 8, so 2n = 16)."
            },
            // Card 16: Module 2, Q7
            {
                id: 16,
                module: 'm2',
                sectionName: 'Math: Module 2',
                desmosLatex: '(d-30)(d+30)',
                title: "Card 16 (Module 2, Question 7): Difference of Squares Expansion",
                problem: "Which expression is equivalent to (d - 30)(d + 30)?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Identify Factoring Identity",
                    prompt: "Identify the product identity for (a - b)(a + b):",
                    options: [
                        "(a - b)(a + b) = a^2 + b^2",
                        "(a - b)(a + b) = a^2 - 2ab + b^2",
                        "(a - b)(a + b) = a^2 - b^2 (Difference of squares)",
                        "(a - b)(a + b) = a^2 + 2ab + b^2"
                    ],
                    correct: 2 // Option C
                },
                step2: {
                    tag: "Step 2: Substitute a = d and b = 30",
                    prompt: "Apply the formula: (d)^2 - (30)^2:",
                    options: [
                        "d^2 - 30",
                        "d^2 - (30)^2",
                        "d^2 - 60d - 900",
                        "2d - 900"
                    ],
                    correct: 1 // Option B
                },
                step3: {
                    tag: "Step 3: Evaluate Constant Term",
                    prompt: "Calculate 30^2 = 900 to give the expanded polynomial:",
                    options: [
                        "d^2 + 900",
                        "d^2 - 60",
                        "d^2 - 900",
                        "d^2 - 300"
                    ],
                    correct: 2 // Option C
                },
                rationale: "(d - 30)(d + 30) is the factored form of a difference of squares: d^2 - 30^2 = d^2 - 900."
            },
            // Card 17: Module 2, Q11
            {
                id: 17,
                module: 'm2',
                sectionName: 'Math: Module 2',
                desmosLatex: 'y=15x+15',
                title: "Card 17 (Module 2, Question 11): Scatterplot Residual / Line of Best Fit",
                problem: "The scatterplot shows data points and the line of best fit for time spent studying (hours) vs. test scores. For the student who studied for 4 hours, what is the difference between the actual test score and the score predicted by the line of best fit?",
                graphSVG: generateSATGridSVG([
                    { type: 'line', x1: 0, y1: 15, x2: 6, y2: 105, color: '#1e3a8a', width: 2.5 },
                    { type: 'point', x: 1, y: 32, color: '#d97706', r: 4 },
                    { type: 'point', x: 2, y: 44, color: '#d97706', r: 4 },
                    { type: 'point', x: 3, y: 62, color: '#d97706', r: 4 },
                    { type: 'point', x: 4, y: 82, color: '#dc2626', r: 5, label: 'Actual (4, 82)' },
                    { type: 'point', x: 4, y: 75, color: '#1e3a8a', r: 4, label: 'Predicted (4, 75)' },
                    { type: 'point', x: 5, y: 88, color: '#d97706', r: 4 }
                ], [0, 6], [0, 110], 300, 260),
                step1: {
                    tag: "Step 1: Read Predicted Value from Trendline",
                    prompt: "At x = 4 hours, find the y-value on the line of best fit:",
                    options: [
                        "Predicted score = 75",
                        "Predicted score = 82",
                        "Predicted score = 70",
                        "Predicted score = 80"
                    ],
                    correct: 0 // Option A
                },
                step2: {
                    tag: "Step 2: Read Actual Data Point",
                    prompt: "Locate the actual plotted data point at x = 4 hours:",
                    options: [
                        "Actual score = 75",
                        "Actual score = 82",
                        "Actual score = 85",
                        "Actual score = 78"
                    ],
                    correct: 1 // Option B
                },
                step3: {
                    tag: "Step 3: Compute Difference (Residual)",
                    prompt: "Calculate Actual Score - Predicted Score = 82 - 75 = [ _____ ]:",
                    options: [
                        "Difference = 10 points",
                        "Difference = 5 points",
                        "Difference = 7 points",
                        "Difference = 12 points"
                    ],
                    correct: 2 // Option C
                },
                rationale: "From the graph, at x = 4, the line of best fit passes through y = 75, while the actual scatterplot point is at y = 82. The difference is 82 - 75 = 7."
            },
            // Card 18: Module 2, Q16
            {
                id: 18,
                module: 'm2',
                sectionName: 'Math: Module 2',
                desmosLatex: '42+68+R=180',
                title: "Card 18 (Module 2, Question 16): Triangle Angle Sum Theorem",
                problem: "In triangle PQR, the measure of angle P is 42° and the measure of angle Q is 68°. What is the measure of angle R?",
                graphSVG: `<svg width="260" height="130" viewBox="0 0 260 130">
                    <polygon points="30,105 230,105 130,25" fill="#f8fafc" stroke="#1e3a8a" stroke-width="2.5"/>
                    <text x="20" y="115" font-size="11" font-weight="bold">P</text>
                    <text x="235" y="115" font-size="11" font-weight="bold">Q</text>
                    <text x="125" y="18" font-size="11" font-weight="bold">R</text>
                    <text x="50" y="98" font-size="10" font-weight="bold" fill="#dc2626">42°</text>
                    <text x="195" y="98" font-size="10" font-weight="bold" fill="#059669">68°</text>
                    <text x="123" y="45" font-size="10" font-weight="bold" fill="#d97706">R = ?</text>
                </svg>`,
                step1: {
                    tag: "Step 1: Triangle Sum Theorem",
                    prompt: "What is the sum of the interior angle measures of any triangle?",
                    options: [
                        "Angle sum = 90°",
                        "Angle sum = 360°",
                        "Angle sum = 180°",
                        "Angle sum = 270°"
                    ],
                    correct: 2 // Option C
                },
                step2: {
                    tag: "Step 2: Add Known Angles",
                    prompt: "Calculate the sum of angles P and Q: 42° + 68°:",
                    options: [
                        "42° + 68° = 110°",
                        "42° + 68° = 100°",
                        "42° + 68° = 120°",
                        "42° + 68° = 112°"
                    ],
                    correct: 0 // Option A
                },
                step3: {
                    tag: "Step 3: Solve for Angle R",
                    prompt: "Subtract: 180° - 110° = [ _____ ]:",
                    options: [
                        "Measure of angle R = 80°",
                        "Measure of angle R = 70°",
                        "Measure of angle R = 60°",
                        "Measure of angle R = 75°"
                    ],
                    correct: 1 // Option B
                },
                rationale: "The interior angles of a triangle sum to 180°: ∠P + ∠Q + ∠R = 180° ⇒ 42° + 68° + ∠R = 180° ⇒ 110° + ∠R = 180° ⇒ ∠R = 70°."
            }
        ];

        let currentUser = null;
        let currentFilteredIndices = [];
        let currentPointer = 0;
        let activeFilter = 'both';
        let userState = { answers: {}, status: {}, cardSteps: {} };
        let desmosCalc = null;

        function initDesmos() {
            const elt = document.getElementById('desmos-calculator');
            if (elt && !desmosCalc && window.Desmos) {
                desmosCalc = Desmos.GraphingCalculator(elt, {
                    expressions: true,
                    keypad: false,
                    settingsMenu: false
                });
            }
            if (desmosCalc && questionsData[currentFilteredIndices[currentPointer]]?.desmosLatex) {
                desmosCalc.setBlank();
                desmosCalc.setExpression({ id: 'fn', latex: questionsData[currentFilteredIndices[currentPointer]].desmosLatex });
            }
        }

        // Calculator Functions
        function calcInput(val) {
            const d = document.getElementById('calc-disp');
            if (d.value === '0' || d.value === 'Error') d.value = val;
            else d.value += val;
        }

        function calcClear() {
            document.getElementById('calc-disp').value = '0';
        }

        function calcEval() {
            const d = document.getElementById('calc-disp');
            try {
                d.value = eval(d.value);
            } catch(e) {
                d.value = 'Error';
            }
        }

        function calcSqrt() {
            const d = document.getElementById('calc-disp');
            try {
                const val = parseFloat(d.value) || 0;
                d.value = Number(Math.sqrt(val).toFixed(4));
            } catch(e) {
                d.value = 'Error';
            }
        }

        function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('email-input').value.trim();
            const moduleChoice = document.getElementById('module-select').value;
            if (email) {
                currentUser = email;
                activeFilter = moduleChoice;
                localStorage.setItem('bm_sat5_email', email);
                initSession();
            }
        }

        function initSession() {
            document.getElementById('display-user-email').innerText = currentUser;
            document.getElementById('user-header-info').style.display = 'flex';

            const savedData = localStorage.getItem(`${currentUser}_${CHAPTER_KEY}`);
            if (savedData) {
                userState = JSON.parse(savedData);
            } else {
                userState = { answers: {}, status: {}, cardSteps: {} };
            }

            switchScreen('quiz-screen');
            setQuizFilter(activeFilter);
            setTimeout(initDesmos, 300);
        }

        function setQuizFilter(filter) {
            activeFilter = filter;
            document.getElementById('tab-all').className = 'switch-tab' + (filter === 'both' ? ' active-tab' : '');
            document.getElementById('tab-m1').className = 'switch-tab' + (filter === 'm1' ? ' active-tab' : '');
            document.getElementById('tab-m2').className = 'switch-tab' + (filter === 'm2' ? ' active-tab' : '');

            currentFilteredIndices = [];
            questionsData.forEach((q, idx) => {
                if (filter === 'both' || q.module === filter) {
                    currentFilteredIndices.push(idx);
                }
            });

            currentPointer = 0;
            renderGrid();
            loadCardByPointer(currentPointer);
        }

        function logout() {
            localStorage.removeItem('bm_sat5_email');
            currentUser = null;
            document.getElementById('user-header-info').style.display = 'none';
            switchScreen('auth-screen');
        }

        function saveState() {
            if (currentUser) {
                localStorage.setItem(`${currentUser}_${CHAPTER_KEY}`, JSON.stringify(userState));
            }
        }

        function switchScreen(id) {
            document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');
        }

        function renderGrid() {
            const grid = document.getElementById('question-grid');
            grid.innerHTML = '';
            currentFilteredIndices.forEach((realIdx, ptr) => {
                const btn = document.createElement('button');
                btn.className = 'grid-btn';
                btn.innerText = realIdx + 1;

                if (ptr === currentPointer) btn.classList.add('active');
                if (userState.status[realIdx] === 'submitted') btn.classList.add('attempted');
                if (userState.status[realIdx] === 'skipped') btn.classList.add('skipped');

                btn.onclick = () => {
                    currentPointer = ptr;
                    loadCardByPointer(currentPointer);
                };
                grid.appendChild(btn);
            });
        }

        function loadCardByPointer(ptr) {
            currentPointer = ptr;
            const realIdx = currentFilteredIndices[currentPointer];
            const q = questionsData[realIdx];

            document.getElementById('q-number-badge').innerText = `Card ${realIdx + 1} of ${questionsData.length}`;
            document.getElementById('q-section-badge').innerText = q.sectionName;
            document.getElementById('q-title-text').innerHTML = q.title;
            document.getElementById('q-problem-text').innerHTML = q.problem;

            const graphContainer = document.getElementById('q-graph-container');
            if (q.graphSVG) {
                graphContainer.innerHTML = q.graphSVG;
                graphContainer.style.display = 'flex';
            } else {
                graphContainer.style.display = 'none';
                graphContainer.innerHTML = '';
            }

            if (!userState.cardSteps[realIdx]) {
                userState.cardSteps[realIdx] = {
                    s1Selection: null, s1Status: 'unattempted',
                    s2Selection: null, s2Status: 'unattempted',
                    s3Selection: null, s3Status: 'unattempted'
                };
            }

            const cState = userState.cardSteps[realIdx];

            renderStepUI(1, q.step1, cState.s1Selection, cState.s1Status, true);
            const isStep1Passed = cState.s1Status === 'correct' || cState.s1Status === 'skipped';
            renderStepUI(2, q.step2, cState.s2Selection, cState.s2Status, isStep1Passed);
            const isStep2Passed = cState.s2Status === 'correct' || cState.s2Status === 'skipped';
            renderStepUI(3, q.step3, cState.s3Selection, cState.s3Status, isStep2Passed);

            const isCardFinished = userState.status[realIdx] === 'submitted' || userState.status[realIdx] === 'skipped';
            const ratBox = document.getElementById('rationale-container');

            if (isCardFinished) {
                ratBox.style.display = 'block';
                document.getElementById('rationale-text').innerHTML = q.rationale;
                document.getElementById('skip-card-btn').style.display = 'none';
                document.getElementById('next-btn').style.display = 'inline-flex';
            } else {
                ratBox.style.display = 'none';
                document.getElementById('skip-card-btn').style.display = 'inline-flex';
                document.getElementById('next-btn').style.display = 'none';
            }

            if (desmosCalc && q.desmosLatex) {
                desmosCalc.setBlank();
                desmosCalc.setExpression({ id: 'fn', latex: q.desmosLatex });
            }

            renderGrid();
        }

        function renderStepUI(stepNum, stepData, currentSelection, currentStatus, isUnlocked) {
            const block = document.getElementById(`step${stepNum}-block`);
            const container = document.getElementById(`step${stepNum}-options-container`);
            const tag = document.getElementById(`step${stepNum}-status-tag`);
            const prompt = document.getElementById(`step${stepNum}-prompt`);
            const tagLabel = document.getElementById(`step${stepNum}-tag`);
            const actions = document.getElementById(`step${stepNum}-actions`);
            
            container.innerHTML = '';
            tagLabel.innerText = stepData.tag;
            prompt.innerHTML = stepData.prompt;

            if (!isUnlocked) {
                block.className = 'step-block locked';
                tag.innerText = 'Locked';
                tag.style.color = 'var(--text-muted)';
                actions.style.display = 'none';
                return;
            }

            if (currentStatus === 'correct') {
                block.className = 'step-block completed-step';
                tag.innerText = '✓ Correct';
                tag.style.color = 'var(--correct-green)';
                actions.style.display = 'none';
            } else if (currentStatus === 'skipped') {
                block.className = 'step-block skipped-step';
                tag.innerText = 'Skipped';
                tag.style.color = 'var(--skipped-orange)';
                actions.style.display = 'none';
            } else {
                block.className = 'step-block active-step';
                tag.innerText = 'In Progress';
                tag.style.color = 'var(--accent-gold)';
                actions.style.display = 'flex';
            }

            stepData.options.forEach((optText, idx) => {
                const item = document.createElement('div');
                item.className = 'step-option-item';

                if (currentSelection === idx) item.classList.add('selected');

                if (currentStatus === 'correct' || currentStatus === 'skipped') {
                    item.classList.add('disabled');
                    if (idx === stepData.correct) item.classList.add('correct');
                    else if (currentSelection === idx) item.classList.add('incorrect');
                } else if (currentStatus === 'incorrect' && currentSelection === idx) {
                    item.classList.add('incorrect');
                    item.onclick = () => selectStepOption(stepNum, idx);
                } else {
                    item.onclick = () => selectStepOption(stepNum, idx);
                }

                item.innerHTML = `<div class="step-opt-prefix">${String.fromCharCode(65 + idx)}</div><div>${optText}</div>`;
                container.appendChild(item);
            });
        }

        function selectStepOption(stepNum, idx) {
            const realIdx = currentFilteredIndices[currentPointer];
            const cState = userState.cardSteps[realIdx];
            if (stepNum === 1) {
                if (cState.s1Status === 'correct' || cState.s1Status === 'skipped') return;
                cState.s1Selection = idx;
                cState.s1Status = 'unattempted';
            } else if (stepNum === 2) {
                if (cState.s2Status === 'correct' || cState.s2Status === 'skipped') return;
                cState.s2Selection = idx;
                cState.s2Status = 'unattempted';
            } else if (stepNum === 3) {
                if (cState.s3Status === 'correct' || cState.s3Status === 'skipped') return;
                cState.s3Selection = idx;
                cState.s3Status = 'unattempted';
            }
            saveState();
            loadCardByPointer(currentPointer);
        }

        function checkStep(stepNum) {
            const realIdx = currentFilteredIndices[currentPointer];
            const q = questionsData[realIdx];
            const cState = userState.cardSteps[realIdx];

            if (stepNum === 1) {
                if (cState.s1Selection === null) {
                    alert("Please choose an answer for Step 1 first!");
                    return;
                }
                if (cState.s1Selection === q.step1.correct) {
                    cState.s1Status = 'correct';
                    AudioFX.playCorrectBell();
                } else {
                    cState.s1Status = 'incorrect';
                    AudioFX.playIncorrectBell();
                }
            } else if (stepNum === 2) {
                if (cState.s2Selection === null) {
                    alert("Please choose an answer for Step 2 first!");
                    return;
                }
                if (cState.s2Selection === q.step2.correct) {
                    cState.s2Status = 'correct';
                    AudioFX.playCorrectBell();
                } else {
                    cState.s2Status = 'incorrect';
                    AudioFX.playIncorrectBell();
                }
            } else if (stepNum === 3) {
                if (cState.s3Selection === null) {
                    alert("Please choose an answer for Step 3 first!");
                    return;
                }
                if (cState.s3Selection === q.step3.correct) {
                    cState.s3Status = 'correct';
                    userState.status[realIdx] = 'submitted';
                    userState.answers[realIdx] = cState.s3Selection;
                    AudioFX.playCorrectBell();
                } else {
                    cState.s3Status = 'incorrect';
                    AudioFX.playIncorrectBell();
                }
            }
            saveState();
            loadCardByPointer(currentPointer);
        }

        function skipStep(stepNum) {
            const realIdx = currentFilteredIndices[currentPointer];
            const cState = userState.cardSteps[realIdx];
            if (stepNum === 1) {
                cState.s1Status = 'skipped';
                AudioFX.playSkipChime();
            } else if (stepNum === 2) {
                cState.s2Status = 'skipped';
                AudioFX.playSkipChime();
            } else if (stepNum === 3) {
                cState.s3Status = 'skipped';
                userState.status[realIdx] = 'submitted';
                AudioFX.playSkipChime();
            }
            saveState();
            loadCardByPointer(currentPointer);
        }

        function skipEntireCard() {
            const realIdx = currentFilteredIndices[currentPointer];
            const cState = userState.cardSteps[realIdx];
            cState.s1Status = 'skipped';
            cState.s2Status = 'skipped';
            cState.s3Status = 'skipped';
            userState.status[realIdx] = 'skipped';
            saveState();
            AudioFX.playSkipChime();
            nextQuestion();
        }

        function nextQuestion() {
            if (currentPointer < currentFilteredIndices.length - 1) {
                loadCardByPointer(currentPointer + 1);
            } else {
                finishTest();
            }
        }

        function finishTest() {
            switchScreen('review-screen');
            let score = 0;
            const reviewList = document.getElementById('review-list');
            reviewList.innerHTML = '';

            currentFilteredIndices.forEach((realIdx) => {
                const q = questionsData[realIdx];
                const status = userState.status[realIdx];
                const cState = userState.cardSteps[realIdx] || {};
                const isFullyCorrect = cState.s1Status === 'correct' && cState.s2Status === 'correct' && cState.s3Status === 'correct';

                if (isFullyCorrect) score++;

                const card = document.createElement('div');
                card.className = 'review-card';

                let tagHtml = '<span class="status-tag tag-skipped">Skipped</span>';
                if (status === 'submitted') {
                    tagHtml = isFullyCorrect 
                        ? '<span class="status-tag tag-correct">Fully Correct</span>' 
                        : '<span class="status-tag tag-incorrect">Completed with Assistance</span>';
                }

                const s3Answer = cState.s3Selection !== null ? q.step3.options[cState.s3Selection] : 'None';
                const s3Correct = q.step3.options[q.step3.correct];

                card.innerHTML = `
                    <div style="display:flex; justify-content:space-between; margin-bottom:0.5rem;">
                        <strong>${q.title}</strong>
                        ${tagHtml}
                    </div>
                    <p style="font-size:0.9rem; margin-bottom:0.5rem;">${q.problem}</p>
                    <p style="font-size:0.9rem; color:var(--text-muted);">
                        <strong>Your Step 3 Answer:</strong> ${s3Answer} | 
                        <strong>Correct Answer:</strong> ${s3Correct}
                    </p>
                    <div style="margin-top:0.5rem; font-size:0.85rem; background:#f8fafc; padding:0.5rem; border-radius:4px;">
                        <strong>Solution:</strong> ${q.rationale}
                    </div>
                `;
                reviewList.appendChild(card);
            });

            document.getElementById('final-score').innerText = `${score} / ${currentFilteredIndices.length}`;
        }

        function restartQuiz() {
            userState = { answers: {}, status: {}, cardSteps: {} };
            saveState();
            startQuizScreen();
        }

        window.onload = function() {
            const savedUser = localStorage.getItem('bm_sat5_email');
            if (savedUser) {
                currentUser = savedUser;
                initSession();
            }
        };
    </script>
</body>
</html>
