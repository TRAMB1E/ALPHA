<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>А-Спокойствие</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    }

    body {
      background: #ffffff;
      color: #000;
    }

    .app {
      max-width: 430px;         /* под мобильный экран */
      margin: 0 auto;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      position: relative;
      background: #fff;
    }

    .content {
      padding: 12px 16px 80px;  /* отступ под нижнее меню */
    }

    /* Заголовок */
    .title {
      font-size: 24px;
      font-weight: 700;
      line-height: 1.2;
      margin-bottom: 16px;
    }
    .title span.accent {
      color: #ff0000;
    }

    /* Карточки */
    .card {
      background: #ffffff;
      border-radius: 20px;
      padding: 16px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.08);
      margin-bottom: 16px;
    }

    .rings-row {
      display: flex;
      justify-content: space-between;
      gap: 12px;
    }

    .donut-wrapper {
      flex: 1;
      text-align: center;
    }

    .donut-outer {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      background: #8adf3b;
      margin: 0 auto;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .donut-inner {
      width: 70px;
      height: 70px;
      border-radius: 50%;
      background: #ffffff;
    }

    .segment {
      position: absolute;
      top: 12px;
      width: 20px;
      height: 10px;
      border-radius: 5px;
    }

    .segment.s1 { left: 20%; background: #ff7a2f; }
    .segment.s2 { left: 36%; background: #ff4fa3; }
    .segment.s3 { left: 52%; background: #9c5fff; }
    .segment.s4 { left: 68%; background: #3fd1ff; }

    .donut-title {
      margin-top: 8px;
      font-size: 14px;
      font-weight: 500;
    }

    /* Прогресс здоровья */
    .health-label {
      font-weight: 500;
      margin-bottom: 8px;
    }

    .health-row {
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .health-bar-bg {
      flex: 1;
      height: 10px;
      border-radius: 5px;
      background: #e0e0e0;
      overflow: hidden;
    }

    .health-bar-fill {
      width: 100%;
      height: 100%;
      background: #55c851;
    }

    .health-value {
      font-size: 12px;
    }

    .health-heart {
      font-size: 16px;
      color: #ff0000;
    }

    /* Задания дня */
    .tasks-title {
      text-align: center;
      font-size: 18px;
      font-weight: 700;
      margin-bottom: 12px;
    }

    .task-row {
      display: flex;
      align-items: center;
      margin-bottom: 6px;
      gap: 6px;
    }

    .task-bullet {
      font-size: 18px;
    }

    .task-text {
      flex: 1;
      font-size: 14px;
    }

    .checkbox {
      width: 22px;
      height: 22px;
      border-radius: 6px;
      border: 2px solid #55c851;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }
    .checkbox span {
      color: #55c851;
      font-size: 16px;
      font-weight: 700;
      visibility: hidden;
    }
    .checkbox.checked span {
      visibility: visible;
    }

    .dots-row {
      margin-top: 10px;
      display: flex;
      justify-content: center;
      gap: 6px;
    }
    .dot {
      width: 6px;
      height: 6px;
      border-radius: 3px;
      background: #ccc;
    }
    .dot.active {
      background: #000;
    }

    /* Ваше финздоровье */
    .section-title {
      font-size: 20px;
      font-weight: 700;
      margin-bottom: 12px;
    }

    .tiles-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 8px;
      margin-bottom: 16px;
    }

    .tile {
      border-radius: 18px;
      padding: 16px;
      color: #fff;
      font-weight: 700;
      font-size: 16px;
      display: flex;
      align-items: flex-end;
      cursor: pointer;
    }

    .tile.big {
      width: 100%;
      background: #ff7a2f;
      min-height: 90px;
    }

    .tile.small {
      width: calc(50% - 4px);
      min-height: 80px;
    }

    .tile.blue {
      background: #5f8bff;
    }

    .tile.green {
      background: #2fbf5f;
    }

    /* Нижняя навигация */
    .tab-bar {
      position: sticky;
      bottom: 0;
      left: 0;
      right: 0;
      height: 64px;
      display: flex;
      border-top: 1px solid #e0e0e0;
      background: #ffffff;
    }

    .tab-item {
      flex: 1;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-size: 10px;
      color: #999;
      cursor: pointer;
    }

    .tab-icon {
      width: 20px;
      height: 20px;
      border-radius: 50%;
      border: 1.5px solid #999;
      margin-bottom: 2px;
    }

    .tab-item.active {
      color: #000;
      font-weight: 600;
    }

    .tab-item.active .tab-icon {
      border-color: #000;
    }
  </style>
</head>
<body>
  <div class="app">
    <div class="content">
      <!-- Заголовок -->
      <h1 class="title">
        <span class="accent">А-Спокойствие</span> - это<br />
        когда деньги под<br />
        контролем
      </h1>

      <!-- Доходы / Расходы -->
      <div class="card">
        <div class="rings-row">
          <div class="donut-wrapper">
            <div class="donut-outer">
              <div class="donut-inner"></div>
              <div class="segment s1"></div>
              <div class="segment s2"></div>
              <div class="segment s3"></div>
              <div class="segment s4"></div>
            </div>
            <div class="donut-title">Доходы</div>
          </div>
          <div class="donut-wrapper">
            <div class="donut-outer">
              <div class="donut-inner"></div>
              <div class="segment s1"></div>
              <div class="segment s2"></div>
              <div class="segment s3"></div>
              <div class="segment s4"></div>
            </div>
            <div class="donut-title">Расходы</div>
          </div>
        </div>
      </div>

      <!-- Очки здоровья -->
      <div class="card">
        <div class="health-label">Ваши очки здоровья</div>
        <div class="health-row">
          <div class="health-bar-bg">
            <div class="health-bar-fill"></div>
          </div>
          <div class="health-value">100/100</div>
          <div class="health-heart">♥</div>
        </div>
      </div>

      <!-- Задания дня -->
      <div class="card">
        <div class="tasks-title">Задания дня</div>

        <div class="task-row">
          <span class="task-bullet">•</span>
          <span class="task-text">Задача 1: Пройти 1 урок</span>
          <div class="checkbox" data-task="1">
            <span>✓</span>
          </div>
        </div>

        <div class="task-row">
          <span class="task-bullet">•</span>
          <span class="task-text">Задача 2: Внести 100 рублей</span>
          <div class="checkbox" data-task="2">
            <span>✓</span>
          </div>
        </div>

        <div class="dots-row">
          <div class="dot active"></div>
          <div class="dot"></div>
          <div class="dot"></div>
        </div>
      </div>

      <!-- Ваше финздоровье -->
      <div class="section-title">Ваше финздоровье</div>

      <div class="tiles-grid">
        <div class="tile big">
          Планирование<br />и накопления
        </div>
        <div class="tile small blue">
          Календарь<br />поступлений
        </div>
        <div class="tile small green">
          Обучение<br />финздоровью
        </div>
      </div>
    </div>

    <!-- Нижнее меню -->
    <div class="tab-bar">
      <div class="tab-item active">
        <div class="tab-icon"></div>
        <span>Главная</span>
      </div>
      <div class="tab-item">
        <div class="tab-icon"></div>
        <span>Платежи</span>
      </div>
      <div class="tab-item">
        <div class="tab-icon"></div>
        <span>Выгода</span>
      </div>
      <div class="tab-item">
        <div class="tab-icon"></div>
        <span>История</span>
      </div>
      <div class="tab-item">
        <div class="tab-icon"></div>
        <span>Чаты</span>
      </div>
    </div>
  </div>

  <script>
    // Простейшая логика: чекбоксы задач
    document.querySelectorAll(".checkbox").forEach(box => {
      box.addEventListener("click", () => {
        box.classList.toggle("checked");
      });
    });

    // Подсветка активной вкладки внизу (по клику)
    document.querySelectorAll(".tab-item").forEach(tab => {
      tab.addEventListener("click", () => {
        document.querySelectorAll(".tab-item").forEach(t => t.classList.remove("active"));
        tab.classList.add("active");
      });
    });
  </script>
</body>
</html>
