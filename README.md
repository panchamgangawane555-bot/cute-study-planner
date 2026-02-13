<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPSC Prelims Planner | 14-Hr Challenge</title>
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #ffb7b2; /* Pastel Red */
            --secondary: #b5ead7; /* Pastel Green */
            --accent: #c7ceea; /* Pastel Purple */
            --bg: #fff5f5; /* Light Pink/White */
            --text: #555;
            --white: #ffffff;
        }

        body {
            font-family: 'Quicksand', sans-serif;
            background-color: var(--bg);
            color: var(--text);
            margin: 0;
            padding: 0;
            background-image: radial-gradient(#ffe4e1 1px, transparent 1px);
            background-size: 20px 20px;
        }

        /* Header & Alex (The Boyfriend) */
        header {
            background: linear-gradient(135deg, var(--primary), #ff9aa2);
            padding: 20px;
            text-align: center;
            color: white;
            border-bottom-left-radius: 30px;
            border-bottom-right-radius: 30px;
            box-shadow: 0 4px 15px rgba(255, 183, 178, 0.4);
            position: relative;
            overflow: hidden;
        }

        .alex-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            margin-top: 10px;
        }

        .alex-avatar {
            width: 80px;
            height: 80px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 40px;
            border: 4px solid var(--accent);
            animation: float 3s ease-in-out infinite;
        }

        .speech-bubble {
            background: white;
            color: #333;
            padding: 10px 15px;
            border-radius: 15px;
            position: relative;
            max-width: 250px;
            font-weight: 600;
            font-size: 0.9rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .speech-bubble::before {
            content: '';
            position: absolute;
            left: -10px;
            top: 50%;
            transform: translateY(-50%);
            border-width: 10px;
            border-style: solid;
            border-color: transparent white transparent transparent;
        }

        h1 { margin: 0; font-size: 1.8rem; text-shadow: 1px 1px 2px rgba(0,0,0,0.1); }
        h2 { margin: 10px 0 5px; font-size: 1.1rem; opacity: 0.9; }

        /* Main Container */
        .container {
            max-width: 800px;
            margin: 30px auto;
            padding: 0 20px;
        }

        /* Day Tracker */
        .day-tracker {
            background: var(--white);
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            margin-bottom: 25px;
            border: 2px dashed var(--accent);
        }

        .day-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .progress-bar {
            height: 10px;
            background: #eee;
            border-radius: 5px;
            overflow: hidden;
            margin-top: 5px;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--secondary), #98d8c8);
            width: 0%;
            transition: width 0.5s ease;
            border-radius: 5px;
        }

        .days-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 8px;
            margin-top: 15px;
        }

        .day-btn {
            background: #f0f0f0;
            border: none;
            padding: 10px 0;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 600;
            color: #777;
            transition: all 0.2s;
        }

        .day-btn:hover { background: #e0e0e0; }
        
        .day-btn.active {
            background: var(--primary);
            color: white;
            transform: scale(1.05);
            box-shadow: 0 3px 10px rgba(255, 183, 178, 0.5);
        }

        .day-btn.completed {
            background: var(--secondary);
            color: #2d6a4f;
        }

        /* Schedule Section */
        .schedule-card {
            background: var(--white);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            border-left: 5px solid var(--accent);
            transition: transform 0.2s;
        }

        .schedule-card:hover { transform: translateY(-3px); }

        .time-block {
            display: flex;
            align-items: center;
            margin-bottom: 12px;
            padding: 10px;
            background: #fafafa;
            border-radius: 10px;
            cursor: pointer;
            transition: background 0.2s;
        }

        .time-block:hover { background: #f0f0f0; }

        .time-block input[type="checkbox"] {
            width: 20px;
            height: 20px;
            accent-color: var(--primary);
            margin-right: 15px;
            cursor: pointer;
        }

        .time-block label {
            flex-grow: 1;
            font-weight: 600;
            cursor: pointer;
        }

        .time-block.checked label {
            text-decoration: line-through;
            color: #aaa;
        }

        .time-tag {
            background: var(--secondary);
            color: #2d6a4f;
            padding: 2px 8px;
            border-radius: 12px;
            font-size: 0.75rem;
            font-weight: 700;
            margin-left: 10px;
        }

        .csat-tag {
            background: var(--accent);
            color: #4a4a8a;
        }

        /* Motivation Section */
        .motivation-box {
            background: linear-gradient(135deg, #fff9c4, #fff59d);
            padding: 20px;
            border-radius: 20px;
            text-align: center;
            margin-top: 20px;
            border: 2px solid #ffe082;
        }

        .motivation-box h3 { margin-top: 0; color: #5d4037; }
        
        .quote {
            font-style: italic;
            font-size: 1.1rem;
            color: #5d4037;
            margin: 10px 0;
        }

        /* Subject Input */
        .subject-input-container {
            background: var(--white);
            padding: 20px;
            border-radius: 20px;
            margin-bottom: 25px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        input[type="text"] {
            width: 100%;
            padding: 12px;
            border: 2px solid #eee;
            border-radius: 10px;
            font-family: 'Quicksand', sans-serif;
            font-size: 1rem;
            box-sizing: border-box;
        }

        input[type="text"]:focus {
            outline: none;
            border-color: var(--primary);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px;
            color: #999;
            font-size: 0.9rem;
        }

        /* Animations */
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* Responsive */
        @media (max-width: 600px) {
            .days-grid { grid-template-columns: repeat(3, 1fr); }
            .alex-container { flex-direction: column; text-align: center; }
            .speech-bubble { margin-top: 10px; }
            .speech-bubble::before { display: none; }
        }
    </style>
</head>
<body>

    <!-- Header with Alex -->
    <header>
        <h1>UPSC Prelims Planner</h1>
        <h2>14-Hour Challenge • 15 Days • 1 Subject</h2>
        
        <div class="alex-container">
            <div class="speech-bubble" id="alex-message">
                Hi! I'm Alex, your study buddy. Ready to crush Prelims? Let's do this! 💪
            </div>
            <div class="alex-avatar">👨‍🎓</div>
        </div>
    </header>

    <div class="container">
        
        <!-- Subject Input -->
        <div class="subject-input-container">
            <label for="subjectName" style="font-weight: 600; display: block; margin-bottom: 8px;">📚 Enter Your Subject for 15 Days:</label>
            <input type="text" id="subjectName" placeholder="e.g., Modern History, Geography, Polity..." oninput="updateSubject()">
        </div>

        <!-- Day Tracker -->
        <div class="day-tracker">
            <div class="day-header">
                <h3>📅 15-Day Tracker</h3>
                <span id="progress-text">Day 1/15</span>
            </div>
            <div class="progress-bar">
                <div class="progress-fill" id="progress-fill"></div>
            </div>
            <div class="days-grid" id="days-grid">
                <!-- Days will be generated by JS -->
            </div>
        </div>

        <!-- Daily Schedule -->
        <div class="schedule-card">
            <h3>📝 Today's 14-Hour Schedule</h3>
            <p id="subject-display" style="color: var(--primary); font-weight: bold; margin-bottom: 15px;">Subject: Not Selected</p>
            
            <div class="time-block" onclick="toggleCheck(this)">
                <input type="checkbox" id="task1">
                <label for="task1">Study Block 1 (3 Hours)</label>
                <span class="time-tag">Morning</span>
            </div>
            
            <div class="time-block" onclick="toggleCheck(this)">
                <input type="checkbox" id="task2">
                <label for="task2">Study Block 2 (3 Hours)</label>
                <span class="time-tag">Afternoon</span>
            </div>
            
            <div class="time-block" onclick="toggleCheck(this)">
                <input type="<span class="time-tag">MCQ Practice</span>">
                <label for="task3">MCQ Practice (3 Hours)</label>
                <span class="time-tag">Evening</span>
            </div>
            
            <div class="time-block" onclick="toggleCheck(this)">
                <input type="checkbox" id="task4">
                <label for="task4">Study Block 3 (3 Hours)</label>
                <span class="time-tag">Night</span>
            </div>
            
            <div class="time-block" onclick="toggleCheck(this)">
                <input type="checkbox" id="task5">
                <label for="task5">CSAT Practice (2 Hours)</label>
                <span class="time-tag csat-tag">CSAT</span>
            </div>
        </div>

        <!-- Motivation -->
        <div class="motivation-box">
            <h3>✨ Alex's Motivation ✨</h3>
            <p class="quote" id="quote-text">"The journey of a thousand miles begins with a single step."</p>
            <p id="alex-encouragement">You're doing great! Keep going!</p>
        </div>

    </div>

    <footer>
        Made with ❤️ for UPSC Aspirants | Stay Consistent!
    </footer>

    <script>
        // --- 1. Subject & Day Logic ---
        let currentDay = 1;
        const totalDays = 15;
        let subject = "";

        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            loadState();
            renderDays();
            updateProgress();
            updateSubjectDisplay();
            rotateQuotes();
        });

        function updateSubject() {
            subject = document.getElementById('subjectName').value;
            updateSubjectDisplay();
            saveState();
        }

        function updateSubjectDisplay() {
            const display = document.getElementById('subject-display');
            if(subject) {
                display.textContent = `Subject: ${subject} (Day ${currentDay})`;
            } else {
                display.textContent = "Subject: Not Selected";
            }
        }

        function renderDays() {
            const grid = document.getElementById('days-grid');
            grid.innerHTML = '';
            for(let i = 1; i <= totalDays; i++) {
                const btn = document.createElement('button');
                btn.className = 'day-btn';
                btn.textContent = i;
                btn.onclick = () => selectDay(i);
                
                // Check if this day is completed (saved in localStorage)
                const isCompleted = localStorage.getItem(`day-${i}-completed`) === 'true';
                if(isCompleted) btn.classList.add('completed');
                
                if(i === currentDay) btn.classList.add('active');
                
                grid.appendChild(btn);
            }
        }

        function selectDay(day) {
            currentDay = day;
            renderDays();
            updateProgress();
            updateSubjectDisplay();
            // Reset checkboxes for the new day
            resetCheckboxes();
            saveState();
        }

        function updateProgress() {
            const progress = (currentDay / totalDays) * 100;
            document.getElementById('progress-fill').style.width = `${progress}%`;
            document.getElementById('progress-text').textContent = `Day ${currentDay}/15`;
        }

        // --- 2. Checkbox Logic (Persistence) ---
        function toggleCheck(element) {
            const checkbox = element.querySelector('input[type="checkbox"]');
            checkbox.checked = !checkbox.checked;
            element.classList.toggle('checked', checkbox.checked);
            
            // Save state of this specific task for this day
            const taskId = checkbox.id;
            const dayKey = `day-${currentDay}-${taskId}`;
            localStorage.setItem(dayKey, checkbox.checked);
            
            // Check if all tasks are done for the day
            checkDayCompletion();
            saveState();
        }

        function checkDayCompletion() {
            const checkboxes = document.querySelectorAll('.time-block input[type="checkbox"]');
            let allChecked = true;
            checkboxes.forEach(cb => {
                if(!cb.checked) allChecked = false;
            });

            if(allChecked) {
                // Mark day as completed
                localStorage.setItem(`day-${currentDay}-completed`, 'true');
                // Update UI
                renderDays();
                // Move to next day automatically after a short delay
                if(currentDay < totalDays) {
                    setTimeout(() => {
                        selectDay(currentDay + 1);
                        alert("🎉 Day Complete! Great job! Moving to Day " + (currentDay+1));
                    }, 1000);
                } else {
                    alert("🎊 Congratulations! You've completed all 15 days of your study plan!");
                }
            }
        }

        function resetCheckboxes() {
            const checkboxes = document.querySelectorAll('.time-block input[type="checkbox"]');
            checkboxes.forEach(cb => {
                cb.checked = false;
                cb.parentElement.classList.remove('checked');
            });
        }

        // --- 3. Alex's Messages & Quotes ---
        const quotes = [
            "The journey of a thousand miles begins with a single step.",
            "Success is the sum of small efforts, repeated day in and day out.",
            "Believe you can and you're halfway there.",
            "The future depends on what you do today.",
            "Don't watch the clock; do what it does. Keep going.",
            "Motivation gets you started. Habit keeps you going."
        ];

        const alexMessages = [
            "You've got this! I believe in you! 💪",
            "Focus up! Let's get that 14 hours in! 📚",
            "I'm so proud of you for sticking to the plan! 🌟",
            "One day at a time. You're building your future! 🏛️",
            "Don't forget to take a small break! Hydrate! 💧",
            "I'm here cheering you on! Let's go! 🎉"
        ];

        function rotateQuotes() {
            const quoteEl = document.getElementById('quote-text');
            const msgEl = document.getElementById('alex-encouragement');
            
            setInterval(() => {
                const randQ = quotes[Math.floor(Math.random() * quotes.length)];
                const randM = alexMessages[Math.floor(Math.random() * alexMessages.length)];
                
                quoteEl.style.opacity = 0;
                msgEl.style.opacity = 0;
                
                setTimeout(() => {
                    quoteEl.textContent = `"${randQ}"`;
                    msgEl.textContent = randM;
                    quoteEl.style.opacity = 1;
                    msgEl.style.opacity = 1;
                }, 300);
            }, 8000); // Change every 8 seconds
        }

        // --- 4. Local Storage (Save Progress) ---
        function saveState() {
            localStorage.setItem('upsc-subject', subject);
            localStorage.setItem('upsc-current-day', currentDay);
        }

        function loadState() {
            const savedSubject = localStorage.getItem('upsc-subject');
            const savedDay = localStorage.getItem('upsc-current-day');
            
            if(savedSubject) {
                subject = savedSubject;
                document.getElementById('subjectName').value = subject;
            }
            if(savedDay) {
                currentDay = parseInt(savedDay);
            }
        }
    </script>
</body>
</html>
