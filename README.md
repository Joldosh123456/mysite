[index.html](https://github.com/user-attachments/files/28501494/index.html)
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Globus B2B — оформление заказа</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      background: #f4f7fb;
      color: #1f2937;
    }

    .topbar {
      background: #0f3b78;
      color: #fff;
      padding: 18px 32px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 24px;
      font-weight: 700;
    }

    .logo span {
      color: #facc15;
    }

    .client {
      text-align: right;
      font-size: 14px;
      line-height: 1.5;
    }

    .container {
      max-width: 1280px;
      margin: 24px auto;
      padding: 0 20px;
    }

    .title {
      margin-bottom: 20px;
    }

    .title h1 {
      font-size: 30px;
      margin-bottom: 6px;
    }

    .title p {
      color: #6b7280;
      font-size: 15px;
    }

    .stepper {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 12px;
      margin-bottom: 24px;
    }

    .step {
      background: #fff;
      border: 1px solid #c7dcff;
      color: #1d4ed8;
      border-radius: 14px;
      padding: 16px 18px;
      font-weight: 700;
      box-shadow: 0 4px 12px rgba(15, 59, 120, 0.05);
    }

    .step.inactive {
      color: #6b7280;
      background: #f8fafc;
      border-color: #e5e7eb;
      font-weight: 500;
    }

    .grid {
      display: grid;
      grid-template-columns: 2fr 1fr;
      gap: 22px;
      align-items: start;
    }

    .section {
      background: #fff;
      border-radius: 16px;
      padding: 22px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.06);
      margin-bottom: 22px;
    }

    .section h2 {
      font-size: 20px;
      margin-bottom: 16px;
      color: #0f3b78;
    }

    .form-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 14px;
    }

    .field {
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    .full {
      grid-column: 1 / -1;
    }

    label {
      font-size: 13px;
      color: #4b5563;
    }

    input,
    textarea,
    select {
      padding: 11px 12px;
      border: 1px solid #d1d5db;
      border-radius: 10px;
      font-size: 14px;
      background: #fff;
    }

    input[readonly],
    select:disabled {
      background: #f3f4f6;
      color: #6b7280;
    }

    textarea {
      resize: vertical;
      min-height: 84px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      font-size: 14px;
    }

    th, td {
      padding: 13px;
      border-bottom: 1px solid #e5e7eb;
      text-align: left;
    }

    th {
      background: #f9fafb;
      color: #374151;
    }

    .qty {
      width: 80px;
    }

    .note {
      margin-top: 14px;
      padding: 13px;
      border-radius: 10px;
      background: #eff6ff;
      border-left: 4px solid #2563eb;
      color: #1e3a8a;
      font-size: 14px;
      line-height: 1.45;
    }

    .warning {
      margin-top: 14px;
      padding: 13px;
      border-radius: 10px;
      background: #fffbeb;
      color: #92400e;
      border-left: 4px solid #f59e0b;
      font-size: 14px;
      line-height: 1.45;
    }

    .summary-line {
      display: flex;
      justify-content: space-between;
      padding: 10px 0;
      border-bottom: 1px solid #e5e7eb;
      font-size: 15px;
    }

    .summary-line.total {
      border-bottom: none;
      font-weight: 700;
      font-size: 20px;
      margin-top: 8px;
    }

    .btn {
      width: 100%;
      border: none;
      border-radius: 12px;
      padding: 14px 16px;
      font-size: 16px;
      font-weight: 700;
      background: #2563eb;
      color: #fff;
      cursor: pointer;
      margin-top: 14px;
    }

    .btn:hover {
      background: #1d4ed8;
    }

    .btn.secondary {
      background: #e5e7eb;
      color: #111827;
    }

    .status {
      display: inline-block;
      padding: 6px 10px;
      border-radius: 999px;
      background: #dcfce7;
      color: #166534;
      font-size: 12px;
      font-weight: 700;
    }

    .checkbox {
      display: flex;
      align-items: flex-start;
      gap: 8px;
      margin-top: 16px;
      font-size: 14px;
      color: #374151;
      line-height: 1.4;
    }

    .checkbox input {
      margin-top: 2px;
    }

    .history-table td,
    .history-table th {
      font-size: 13px;
      padding: 10px;
    }

    @media (max-width: 900px) {
      .topbar {
        flex-direction: column;
        align-items: flex-start;
        gap: 10px;
      }

      .client {
        text-align: left;
      }

      .grid,
      .form-grid,
      .stepper {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <header class="topbar">
    <div class="logo">GLOBUS <span>B2B</span></div>
    <div class="client">
      <strong>ОсОО «Альфа Трейд»</strong><br />
      ИНН: 01234567890123 · Карта лояльности: B2B-000458
    </div>
  </header>

  <main class="container">
    <div class="title">
      <h1>Оформление корпоративного заказа</h1>
      <p>Проверьте корзину, заполните данные доставки и доверенного лица, затем подтвердите заказ.</p>
    </div>

    <div class="stepper">
      <div class="step">1. Корзина</div>
      <div class="step">2. Данные КК</div>
      <div class="step">3. Доверенность</div>
      <div class="step inactive">4. Подтверждение</div>
    </div>

    <div class="grid">
      <div>
        <section class="section">
          <h2>1. Корзина</h2>
          <table>
            <thead>
              <tr>
                <th>Товар</th>
                <th>Кол-во</th>
                <th>Цена</th>
                <th>Сумма</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>Вода питьевая 5 л</td>
                <td><input class="qty" type="number" value="10" min="1" /></td>
                <td>65 сом</td>
                <td>650 сом</td>
              </tr>
              <tr>
                <td>Сахар 1 кг</td>
                <td><input class="qty" type="number" value="20" min="1" /></td>
                <td>78 сом</td>
                <td>1 560 сом</td>
              </tr>
              <tr>
                <td>Чай черный 100 пак.</td>
                <td><input class="qty" type="number" value="5" min="1" /></td>
                <td>320 сом</td>
                <td>1 600 сом</td>
              </tr>
            </tbody>
          </table>
        </section>

        <section class="section">
          <h2>2. Данные корпоративного клиента</h2>
          <div class="form-grid">
            <div class="field">
              <label>Наименование организации</label>
              <input type="text" value="ОсОО «Альфа Трейд»" readonly />
            </div>
            <div class="field">
              <label>ИНН</label>
              <input type="text" value="01234567890123" readonly />
            </div>
            <div class="field">
              <label>Email</label>
              <input type="email" value="buh@alfa.kg" readonly />
            </div>
            <div class="field">
              <label>Вид оплаты</label>
              <select disabled>
                <option>Безналичный расчет</option>
              </select>
            </div>
            <div class="field full">
              <label>Юридический адрес</label>
              <input type="text" value="г. Бишкек, ул. Киевская 100" readonly />
            </div>
          </div>

          <div class="note">
            Данные КК заведены в портале и в 1С. Вид оплаты закрепляется договором и не изменяется клиентом вручную.
          </div>
        </section>

        <section class="section">
          <h2>Контактные лица по заказу</h2>
          <div class="form-grid">
            <div class="field">
              <label>Руководитель</label>
              <input type="text" placeholder="ФИО руководителя" />
            </div>
            <div class="field">
              <label>Телефон руководителя</label>
              <input type="tel" placeholder="+996 ..." />
            </div>
            <div class="field">
              <label>Бухгалтер</label>
              <input type="text" placeholder="ФИО бухгалтера" />
            </div>
            <div class="field">
              <label>Телефон бухгалтера</label>
              <input type="tel" placeholder="+996 ..." />
            </div>
            <div class="field">
              <label>Закупщик</label>
              <input type="text" placeholder="ФИО закупщика" />
            </div>
            <div class="field">
              <label>Телефон закупщика</label>
              <input type="tel" placeholder="+996 ..." />
            </div>
          </div>
        </section>

        <section class="section">
          <h2>Адрес доставки</h2>
          <div class="form-grid">
            <div class="field full">
              <label>Адрес доставки</label>
              <input type="text" placeholder="Например: г. Бишкек, ул. Логвиненко 25, офис 3" />
            </div>
            <div class="field full">
              <label>Комментарий к доставке</label>
              <textarea placeholder="Например: позвонить за 15 минут, вход со двора"></textarea>
            </div>
          </div>
          <div class="note">
            Адрес доставки вводится вручную, потому что у одной организации может быть несколько филиалов.
          </div>
        </section>

        <section class="section">
          <h2>3. Доверенное лицо для получения товара</h2>
          <div class="form-grid">
            <div class="field">
              <label>ФИО доверенного лица</label>
              <input type="text" placeholder="ФИО получателя" />
            </div>
            <div class="field">
              <label>Телефон получателя</label>
              <input type="tel" placeholder="+996 ..." />
            </div>
            <div class="field">
              <label>Номер доверенности</label>
              <input type="text" placeholder="Например: ДОВ-2026-045" />
            </div>
            <div class="field">
              <label>Срок действия доверенности</label>
              <input type="date" />
            </div>
            <div class="field full">
              <label>Скан-копия доверенности</label>
              <input type="file" accept=".pdf,.jpg,.jpeg,.png" />
            </div>
          </div>
          <div class="warning">
            При доставке доверенное лицо должно предоставить курьеру оригинал доверенности и документ, удостоверяющий личность.
          </div>
        </section>

        <section class="section">
          <h2>История заказов</h2>
          <table class="history-table">
            <thead>
              <tr>
                <th>№ заказа</th>
                <th>Дата</th>
                <th>Сумма</th>
                <th>Статус</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>B2B-10245</td>
                <td>28.05.2026</td>
                <td>45 800 сом</td>
                <td>Доставлен</td>
              </tr>
              <tr>
                <td>B2B-10212</td>
                <td>21.05.2026</td>
                <td>18 300 сом</td>
                <td>Закрыт</td>
              </tr>
            </tbody>
          </table>
        </section>
      </div>

      <aside>
        <section class="section">
          <h2>4. Подтверждение</h2>

          <div class="summary-line">
            <span>Товаров</span>
            <span>35 шт.</span>
          </div>
          <div class="summary-line">
            <span>Сумма товаров</span>
            <span>3 810 сом</span>
          </div>
          <div class="summary-line">
            <span>Скидка / бонус</span>
            <span>0 сом</span>
          </div>
          <div class="summary-line total">
            <span>Итого</span>
            <span>3 810 сом</span>
          </div>

          <div class="note">
            Заказы, оформленные до 11:00, передаются на сборку и доставляются в течение дня. Если доставка не успевает, заказ переносится на следующий день.
          </div>

          <label class="checkbox">
            <input type="checkbox" />
            <span>Подтверждаю корректность товаров, адреса доставки и данных доверенного лица.</span>
          </label>

          <button class="btn">Подтвердить заказ</button>
          <button class="btn secondary">Вернуться в каталог</button>
        </section>

        <section class="section">
          <h2>Передача в 1С</h2>
          <p><span class="status">Готов к передаче</span></p>
          <div class="note">
            После подтверждения заказ будет сохранен в истории и передан в 1С по существующему механизму обмена B2C с доработками под B2B.
          </div>
        </section>
      </aside>
    </div>
  </main>
</body>
</html>
