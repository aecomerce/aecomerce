<div align="center">

# Arkadiy Fesler

### Python Backend Developer • Data Analyst

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=22&duration=3000&pause=1000&color=58A6FF&center=true&vCenter=true&width=700&lines=Python+Backend+Developer;FastAPI+%7C+PostgreSQL+%7C+Docker;Data+Analysis+%7C+Automation+%7C+APIs;Building+Scalable+and+Reliable+Systems" />

</div>

---

<!-- СТИЛЬНАЯ АНИМАЦИЯ: ТЕРМИНАЛ-СТАТУС БЭКЕНД/ДАТА -->
<div align="center">
  <table style="background: #0D1117; border-radius: 20px; border: 1px solid #30363d; max-width: 800px; margin: 20px auto; backdrop-filter: blur(4px);">
    <tr>
      <td style="padding: 20px 24px;">
        <div style="font-family: 'JetBrains Mono', 'Fira Code', monospace; font-size: 14px;">

          <!-- Заголовок терминала с точками -->
          <div style="display: flex; align-items: center; gap: 8px; margin-bottom: 16px; border-bottom: 1px solid #21262d; padding-bottom: 10px;">
            <span style="display: inline-block; width: 12px; height: 12px; background: #ff5f56; border-radius: 50%;"></span>
            <span style="display: inline-block; width: 12px; height: 12px; background: #ffbd2e; border-radius: 50%;"></span>
            <span style="display: inline-block; width: 12px; height: 12px; background: #27c93f; border-radius: 50%;"></span>
            <span style="color: #8b949e; margin-left: 12px; font-size: 12px;">🐍 backend@analyst:~/resume</span>
          </div>

          <!-- Анимированные строки (классический массив + цикл) -->
          <div style="color: #e6edf3; line-height: 1.6;">
            <span style="color: #58a6ff;">$</span> 
            <span id="animated-line" style="color: #c9d1d9;"></span>
            <span style="display: inline-block; width: 10px; height: 16px; background-color: #58a6ff; vertical-align: middle; margin-left: 2px; animation: blink 1s step-end infinite;"></span>
          </div>

          <!-- Доп. строка с прогрессом (динамическая нагрузка) -->
          <div style="margin-top: 20px;">
            <div style="display: flex; justify-content: space-between; font-size: 12px; color: #8b949e; margin-bottom: 6px;">
              <span>▶ DATA PIPELINE HEALTH</span>
              <span id="progress-percent" style="color: #58a6ff;">98%</span>
            </div>
            <div style="background: #21262d; border-radius: 12px; height: 6px; overflow: hidden;">
              <div id="progress-bar" style="width: 98%; background: linear-gradient(90deg, #3fb950, #58a6ff); height: 6px; border-radius: 12px;"></div>
            </div>
          </div>

          <div style="margin-top: 14px; display: flex; gap: 16px; flex-wrap: wrap; font-size: 11px; color: #7d8590; border-top: 1px solid #21262d; padding-top: 12px;">
            <span>🔄 ETL: <span id="etl-status" style="color: #3fb950;">active</span></span>
            <span>📊 API req/s: <span id="api-rps" style="color: #f0883e;">142</span></span>
            <span>🐍 Tests: <span id="test-status" style="color: #d2a8ff;">✅ 23 passed</span></span>
          </div>

        </div>
      </td>
    </tr>
  </table>
</div>

<style>
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }
</style>

<script>
  (function() {
    // 1. Анимация печати строк (массив технологий / действий)
    const lines = [
      "Initializing FastAPI core... ✔️",
      "Loading PostgreSQL pool → 12 connections",
      "Running pandas profiling on sales data... 📈",
      "Building ML feature store (scikit-learn) ✅",
      "Docker Compose up: 4 services ready 🐳",
      "System ready. Last deploy: main@2025-02-18"
    ];
    
    let lineIndex = 0;
    let charIndex = 0;
    const animatedSpan = document.getElementById('animated-line');
    let intervalId = null;
    
    function typeNextLine() {
      if (!animatedSpan) return;
      if (lineIndex >= lines.length) {
        // закончили — через 2 секунды повторяем с начала (эффект цикла)
        setTimeout(() => {
          lineIndex = 0;
          charIndex = 0;
          if (animatedSpan) animatedSpan.innerHTML = '';
          typeNextLine();
        }, 3000);
        return;
      }
      
      const currentLine = lines[lineIndex];
      if (charIndex < currentLine.length) {
        animatedSpan.innerHTML = currentLine.substring(0, charIndex + 1);
        charIndex++;
        setTimeout(typeNextLine, 55);
      } else {
        // строка напечатана — пауза и следующая
        lineIndex++;
        charIndex = 0;
        setTimeout(typeNextLine, 800);
      }
    }
    
    // 2. Динамический процент (имитация нагрузки: гуляет от 78 до 99)
    const percentSpan = document.getElementById('progress-percent');
    const progressBar = document.getElementById('progress-bar');
    let currentPercent = 98;
    
    function updateMetrics() {
      // Изменение процента (случайные колебания, но в пределах адекватного)
      let delta = (Math.random() - 0.5) * 6;
      let newPercent = currentPercent + delta;
      if (newPercent > 99) newPercent = 97;
      if (newPercent < 78) newPercent = 82;
      currentPercent = Math.floor(newPercent);
      if (percentSpan) percentSpan.innerText = currentPercent + '%';
      if (progressBar) progressBar.style.width = currentPercent + '%';
      
      // Имитация RPS (колеблется)
      const rpsSpan = document.getElementById('api-rps');
      if (rpsSpan) {
        let rps = 120 + Math.floor(Math.random() * 45);
        rpsSpan.innerText = rps;
      }
      
      // Меняем статус ETL иногда
      const etlSpan = document.getElementById('etl-status');
      if (etlSpan && Math.random() < 0.2) {
        etlSpan.innerHTML = (etlSpan.innerHTML === 'active') ? '⚙️ processing' : 'active';
        setTimeout(() => {
          if (etlSpan) etlSpan.innerHTML = 'active';
        }, 1800);
      }
    }
    
    // Запуск печати
    typeNextLine();
    
    // Обновление метрик каждые 3.5 секунды (профессиональный дашборд)
    setInterval(updateMetrics, 3600);
    
    // начальный вызов
    updateMetrics();
    
    // также имитируем смену тестов для реалистичности
    const testSpan = document.getElementById('test-status');
    if (testSpan) {
      setInterval(() => {
        const tests = ['✅ 23 passed', '✅ 27 passed', '✅ 24 passed', '✅ 26 passed'];
        const randomTest = tests[Math.floor(Math.random() * tests.length)];
        testSpan.innerHTML = randomTest;
      }, 5000);
    }
  })();
</script>

## About Me

Passionate Python Developer focused on building backend services, APIs, automation tools, and data-driven applications.

* Backend development with Python & FastAPI
* Database design and optimization
* Data analysis and visualization
* API architecture and integrations
* Automation and scripting
* Basic frontend development experience

---

## Tech Stack

### Backend

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge\&logo=fastapi\&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge\&logo=django\&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=for-the-badge)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge\&logo=redis\&logoColor=white)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=for-the-badge\&logo=graphql\&logoColor=white)

### Data Analysis

![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge\&logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge\&logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge\&logo=jupyter)
![Scikit Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge\&logo=scikitlearn)

### Databases

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge\&logo=postgresql)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge\&logo=mongodb)

### DevOps & Tools

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge\&logo=git)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge\&logo=docker)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge\&logo=linux)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge\&logo=kubernetes)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge\&logo=postman)
![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=for-the-badge\&logo=pytest)

### Frontend

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge\&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge\&logo=typescript)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge\&logo=javascript)

---

## GitHub Activity

<div align="center">

<img src="https://github-readme-activity-graph.vercel.app/graph?username=aecomerce&theme=tokyo-night&hide_border=true"/>

</div>

---

## Contribution Snake

<p align="center">
  <img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake-dark.svg" />
</p>

---

## Connect With Me

[![Telegram](https://img.shields.io/badge/Telegram-26A5E4?style=for-the-badge\&logo=telegram\&logoColor=white)](https://t.me/aecomerce)
