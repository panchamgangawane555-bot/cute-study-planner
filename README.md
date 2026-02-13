# my-study-planer
its a study planer. its cute
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>🌸 Cute Study Planner</title>
  <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
  <style>
    /* ═══════════════════════════════════════ */
    /* 🌸 CUTE STUDY TIMETABLE - STYLES 🌸 */
    /* ═══════════════════════════════════════ */
    
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    :root {
      --pink-light: #fff0f5;
      --pink-main: #ff85a2;
      --pink-dark: #ff5c7c;
      --purple-light: #f3e5f5;
      --purple-main: #ba68c8;
      --blue-light: #e3f2fd;
      --blue-main: #64b5f6;
      --green-light: #e8f5e9;
      --green-main: #81c784;
      --yellow-light: #fffde7;
      --yellow-main: #ffd54f;
      --orange-light: #fff3e0;
      --orange-main: #ffb74d;
      --cream: #fdf5f0;
      --white: #ffffff;
      --text-dark: #4a4a4a;
      --text-light: #8a8a8a;
    }
    
    body {
      font-family: 'Nunito', sans-serif;
      background: var(--cream);
      min-height: 100vh;
      position: relative;
      overflow-x: hidden;
    }
    
    /* Cute background decorations */
    body::before {
      content: '';
      position: fixed;
      top: -50px;
      left: -50px;
      width: 200px;
      height: 200px;
      background: radial-gradient(circle, rgba(255,133,162,0.2) 0%, transparent 70%);
      border-radius: 50%;
      z-index: -1;
    }
    
    body::after {
      content: '';
      position: fixed;
      bottom: -80px;
      right: -80px;
      width: 300px;
      height: 300px;
      background: radial-gradient(circle, rgba(186,104,200,0.15) 0%, transparent 70%);
      border-radius: 50%;
      z-index: -1;
    }
    
    /* Floating decorations */
    .decoration {
      position: fixed;
      font-size: 24px;
      opacity: 0.3;
      z-index: -1;
      animation: float 6s ease-in-out infinite;
    }
    
    .decoration:nth-child(1) { top: 10%; left: 5%; animation-delay: 0s; }
    .decoration:nth-child(2) { top: 30%; right: 8%; animation-delay: 1s; }
    .decoration:nth-child(3) { bottom: 20%; left: 10%; animation-delay: 2s; }
    .decoration:nth-child(4) { bottom: 40%; right: 5%; animation-delay: 3s; }
    
    @keyframes float {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      50% { transform: translateY(-20px) rotate(10deg); }
    }
    
    /* Main Container */
    .app-wrapper {
      max-width: 480px;
      margin: 0 auto;
      padding: 20px;
      min-height: 100vh;
    }
    
    /* Header */
    .header {
      text-align: center;
      padding: 30px 20px;
      background: linear-gradient(135deg, var(--pink-light) 0%, #ffe4ec 100%);
      border-radius: 30px;
      margin-bottom: 25px;
      box-shadow: 0 10px 40px rgba(255,133,162,0.2);
      position: relative;
      overflow: hidden;
    }
    
    .header::before {
      content: '✦';
      position: absolute;
      top: 15px;
      left: 20px;
      color: var(--pink-main);
      font-size: 20px;
    }
    
    .header::after {
      content: '✦';
      position: absolute;
      bottom: 15px;
      right: 20px;
      color: var(--pink-main);
      font-size: 20px;
    }
    
    .mascot {
      font-size: 60px;
      margin-bottom: 10px;
      animation: bounce 2s ease-in-out infinite;
      display: inline-block;
    }
    
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-15px); }
    }
    
    .header h1 {
      font-size: 28px;
      font-weight: 800;
      color: var(--pink-dark);
      margin-bottom: 5px;
      letter-spacing: -0.5px;
    }
    
    .header p {
      color: var(--pink-main);
      font-weight: 600;
      font-size: 14px;
    }
    
    /* Add Task Section */
    .add-task-card {
      background: var(--white);
      border-radius: 25px;
      padding: 25px;
      margin-bottom: 25px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.06);
      border: 2px solid transparent;
      transition: all 0.3s;
    }
    
    .add-task-card:hover {
      border-color: var(--pink-light);
    }
    
    .add-task-card h2 {
      font-size: 18px;
      color: var(--text-dark);
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    
    /* Day Tabs */
    .day-tabs {
      display: flex;
      gap: 6px;
      margin-bottom: 15px;
      flex-wrap: wrap;
    }
    
    .day-tab {
      flex: 1;
      min-width: 45px;
      padding: 10px 5px;
      border: 2px solid var(--pink-light);
      background: var(--white);
      border-radius: 15px;
      font-family: 'Nunito', sans-serif;
      font-weight: 700;
      font-size: 12px;
      color: var(--text-light);
      cursor: pointer;
      transition: all 0.3s;
    }
    
    .day-tab:hover {
      border-color: var(--pink-main);
      color: var(--pink-main);
    }
    
    .day-tab.active {
      background: linear-gradient(135deg, var(--pink-main), var(--pink-dark));
      color: var(--white);
      border-color: var(--pink-main);
      box-shadow: 0 5px 15px rgba(255,92,124,0.3);
    }
    
    /* Input Fields */
    .input-row {
      display: flex;
      gap: 10px;
      margin-bottom: 12px;
    }
    
    .input-field {
      flex: 1;
      padding: 14px 16px;
      border: 2px solid var(--pink-light);
      border-radius: 15px;
      font-family: 'Nunito', sans-serif;
      font-size: 14px;
      font-weight: 600;
      color: var(--text-dark);
      transition: all 0.3s;
      outline: none;
    }
    
    .input-field:focus {
      border-color: var(--pink-main);
      box-shadow: 0 0 0 4px rgba(255,133,162,0.15);
    }
    
    .input-field::placeholder {
      color: #c9c9c9;
    }
    
    input[type="time"] {
      color-scheme: light;
    }
    
    /* Add Button */
    .btn-add {
      width: 100%;
      padding: 16px;
      background: linear-gradient(135deg, var(--pink-main), var(--pink-dark));
      color: var(--white);
      border: none;
      border-radius: 15px;
      font-family: 'Nunito', sans-serif;
      font-size: 16px;
      font-weight: 800;
      cursor: pointer;
      transition: all 0.3s;
      box-shadow: 0 8px 25px rgba(255,92,124,0.35);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }
    
    .btn-add:hover {
      transform: translateY(-3px);
      box-shadow: 0 12px 35px rgba(255,92,124,0.45);
    }
    
    .btn-add:active {
      transform: translateY(0);
    }
    
    /* Timetable Display */
    .timetable-section {
      margin-bottom: 25px;
    }
    
    .day-group {
      margin-bottom: 20px;
    }
    
    .day-title {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 12px;
      padding: 12px 18px;
      border-radius: 15px;
      font-weight: 800;
      font-size: 16px;
    }
    
    .day-title.monday { background: var(--pink-light); color: var(--pink-dark); }
    .day-title.tuesday { background: var(--yellow-light); color: #f9a825; }
    .day-title.wednesday { background: var(--blue-light); color: var(--blue-main); }
    .day-title.thursday { background: var(--purple-light); color: var(--purple-main); }
    .day-title.friday { background: var(--orange-light); color: var(--orange-main); }
    .day-title.saturday { background: var(--green-light); color: var(--green-main); }
    .day-title.sunday { background: #fce4ec; color: #ec407a; }
    
    .task-card {
      background: var(--white);
      border-radius: 18px;
      padding: 16px;
      margin-bottom: 10px;
      display: flex;
      align-items: center;
      gap: 12px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.04);
      animation: slideIn 0.3s ease;
      border-left: 4px solid var(--pink-main);
      transition: all 0.3s;
    }
    
    .task-card:hover {
      transform: translateX(5px);
      box-shadow: 0 6px 20px rgba(0,0,0,0.08);
    }
    
    @keyframes slideIn {
      from {
        opacity: 0;
        transform: translateY(10px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .task-time {
      min-width: 70px;
      padding: 8px 12px;
      background: var(--pink-light);
      border-radius: 12px;
      font-weight: 700;
      font-size: 13px;
      color: var(--pink-dark);
      text-align: center;
    }
    
    .task-details {
      flex: 1;
    }
    
    .task-subject {
      font-weight: 700;
      font-size: 15px;
      color: var(--text-dark);
      margin-bottom: 3px;
    }
    
    .task-note {
      font-size: 12px;
      color: var(--text-light);
    }
    
    .btn-delete {
      width: 36px;
      height: 36px;
      border: none;
      background: var(--pink-light);
      border-radius: 12px;
      cursor: pointer;
      font-size: 16px;
      transition: all 0.3s;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    .btn-delete:hover {
      background: var(--pink-dark);
      color: var(--white);
    }
    
    /* Empty State */
    .empty-state {
      text-align: center;
      padding: 50px 20px;
      color: var(--text-light);
    }
    
    .empty-state .icon {
      font-size: 60px;
      margin-bottom: 15px;
      opacity: 0.5;
    }
    
    .empty-state p {
      font-size: 14px;
      font-weight: 600;
    }
    
    /* Stats Card */
    .stats-card {
      background: linear-gradient(135deg, var(--pink-main), var(--purple-main));
      border-radius: 25px;
      padding: 25px;
      text-align: center;
      color: var(--white);
      box-shadow: 0 10px 40px rgba(186,104,200,0.3);
      margin-bottom: 25px;
    }
    
    .stats-card h3 {
      font-size: 14px;
      font-weight: 600;
      opacity: 0.9;
      margin-bottom: 5px;
    }
    
    .stats-card .number {
      font-size: 48px;
      font-weight: 800;
      line-height: 1;
    }
    
    .stats-card .label {
      font-size: 13px;
      opacity: 0.85;
    }
    
    /* Footer */
    .footer {
      text-align: center;
      padding: 20px;
      color: var(--text-light);
      font-size: 12px;
    }
    
    .footer span {
      color: var(--pink-main);
    }
    
    /* Responsive */
    @media (max-width: 400px) {
      .input-row {
        flex-direction: column;
      }
      
      .day-tab {
        min-width: 40px;
        padding: 8px 4px;
        font-size: 11px;
      }
    }
  </style>
</head>
<body>
  <!-- Floating Decorations -->
  <div class="decoration">🌸</div>
  <div class="decoration">🎀</div>
  <div class="decoration">✨</div>
  <div class="decoration">📚</div>

  <div class="app-wrapper">
    <!-- Header -->
    <div class="header">
      <div class="mascot">📖💕</div>
      <h1>My Study Planner</h1>
      <p>Let's achieve great things together!</p>
    </div>

    <!-- Add Task Card -->
    <div class="add-task-card">
      <h2>➕ Add New Study Session</h2>
      
      <!-- Day Tabs -->
      <div class="day-tabs" id="dayTabs">
        <button class="day-tab active" data-day="monday">Mon</button>
        <button class="day-tab" data-day="tuesday">Tue</button>
        <button class="day-tab" data-day="wednesday">Wed</button>
        <button class="day-tab" data-day="thursday">Thu</button>
        <button class="day-tab" data-day="friday">Fri</button>
        <button class="day-tab" data-day="saturday">Sat</button>
        <button class="day-tab" data-day="sunday">Sun</button>
      </div>
      
      <div class="input-row">
        <input type="text" class="input-field" id="subjectInput" placeholder="📚 Subject name...">
      </div>
      
      <div class="input-row">
        <input type="text" class="input-field" id="noteInput" placeholder="📝 Quick note (optional)">
        <input type="time" class="input-field" id="timeInput">
      </div>
      
      <button class="btn-add" onclick="addTask()">
        ✨ Add to Timetable
      </button>
    </div>

    <!-- Stats -->
    <div class="stats-card">
      <h3>🌟 Weekly Progress</h3>
      <div class="number" id="totalCount">0</div>
      <div class="label">study sessions planned</div>
    </div>

    <!-- Timetable -->
    <div class="timetable-section" id="timetable">
      <!-- Tasks will appear here -->
    </div>

    <!-- Footer -->
    <div class="footer">
      Made with <span>💖</span> for amazing students
    </div>
  </div>

  <script>
    // ═══════════════════════════════════════
    // 🌸 JAVASCRIPT - MAKE IT WORK! 🌸
    // ═══════════════════════════════════════
    
    let currentDay = 'monday';
    
    // Initialize tasks from localStorage or empty object
    let tasks = JSON.parse(localStorage.getItem('cuteStudyTasks')) || {
      monday: [],
      tuesday: [],
      wednesday: [],
      thursday: [],
      friday: [],
      saturday: [],
      sunday: []
    };
    
    const dayNames = {
      monday: 'Monday',
      tuesday: 'Tuesday',
      wednesday: 'Wednesday',
      thursday: 'Thursday',
      friday: 'Friday',
      saturday: 'Saturday',
      sunday: 'Sunday'
    };
    
    const dayEmojis = {
      monday: '🌸',
      tuesday: '🌻',
      wednesday: '🌈',
      thursday: '🍇',
      friday: '⭐',
      saturday: '🎉',
      sunday: '☀️'
    };
    
    // Day tab click handler
    document.querySelectorAll('.day-tab').forEach(tab => {
      tab.addEventListener('click', function() {
        document.querySelectorAll('.day-tab').forEach(t => t.classList.remove('active'));
        this.classList.add('active');
        currentDay = this.dataset.day;
      });
    });
    
    // Add new task
    function addTask() {
      const subject = document.getElementById('subjectInput').value.trim();
      const note = document.getElementById('noteInput').value.trim();
      const time = document.getElementById('timeInput').value;
      
      // Validation
      if (!subject) {
        alert('Please enter a subject! 📚');
        return;
      }
      if (!time) {
        alert('Please pick a time! ⏰');
        return;
      }
      
      // Add task to current day
      tasks[currentDay].push({
        id: Date.now(),
        subject,
        note,
        time
      });
      
      // Sort by time
      tasks[currentDay].sort((a, b) => a.time.localeCompare(b.time));
      
      // Save to localStorage
      saveTasks();
      
      // Clear inputs
      document.getElementById('subjectInput').value = '';
      document.getElementById('noteInput').value = '';
      document.getElementById('timeInput').value = '';
      
      // Re-render
      renderTasks();
    }
    
    // Delete task
    function deleteTask(day, taskId) {
      tasks[day] = tasks[day].filter(task => task.id !== taskId);
      saveTasks();
      renderTasks();
    }
    
    // Save to localStorage
    function saveTasks() {
      localStorage.setItem('cuteStudyTasks', JSON.stringify(tasks));
    }
    
    // Format time to 12-hour format
    function formatTime(time24) {
      const [hours, minutes] = time24.split(':');
      const h = parseInt(hours);
      const ampm = h >= 12 ? 'PM' : 'AM';
      const h12 = h % 12 || 12;
      return `${h12}:${minutes} ${ampm}`;
    }
    
    // Render all tasks
    function renderTasks() {
      const container = document.getElementById('timetable');
      container.innerHTML = '';
      
      let total = 0;
      
      // Loop through each day
      Object.keys(tasks).forEach(day => {
        const dayTasks = tasks[day];
        
        if (dayTasks.length > 0) {
          total += dayTasks.length;
          
          const dayGroup = document.createElement('div');
          dayGroup.className = 'day-group';
          
          let tasksHTML = '';
          dayTasks.forEach(task => {
            tasksHTML += `
              <div class="task-card">
                <div class="task-time">${formatTime(task.time)}</div>
                <div class="task-details">
                  <div class="task-subject">${task.subject}</div>
                  ${task.note ? `<div class="task-note">${task.note}</div>` : ''}
                </div>
                <button class="btn-delete" onclick="deleteTask('${day}', ${task.id})">✕</button>
              </div>
            `;
          });
          
          dayGroup.innerHTML = `
            <div class="day-title ${day}">
              ${dayEmojis[day]} ${dayNames[day]}
            </div>
            ${tasksHTML}
          `;
          
          container.appendChild(dayGroup);
        }
      });
      
      // Update total count
      document.getElementById('totalCount').textContent = total;
      
      // Show empty state if no tasks
      if (total === 0) {
        container.innerHTML = `
          <div class="empty-state">
            <div class="icon">📓</div>
            <p>Your timetable is empty!</p>
            <p>Add your first study session above ✨</p>
          </div>
        `;
      }
    }
    
    // Initial render
    renderTasks();
  </script>
</body>
</html>
