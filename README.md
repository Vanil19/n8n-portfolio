# n8n Portfolio

Здесь я собираю свои проекты автоматизации на [n8n] https://ivan-n8n.site/workflow/APfutCqqCNZUV08h (если пишет опасный сайт нажмите сведения->небезопасный сайт и он у вас откроется)

## 📌 Кейсы

### 1. Telegram Bot → Google Sheets
**Задача:** клиент получает заявки в Telegram, но они теряются.  
**Решение:** настроил автоматизацию: все сообщения записываются в Google Sheets, а пользователю уходит подтверждение.  
**Результат:** заявки больше не теряются, менеджер всегда видит новые обращения.

🔗 [workflow.json](case1-telegram-sheets/workflow.json)  
📸 Скриншот:  
<img width="1920" height="960" alt="image" src="https://github.com/user-attachments/assets/b17f70a6-02e7-4198-b166-2e119cbdbec4" /> - Скрин воркфлоу

<img width="1857" height="917" alt="image" src="https://github.com/user-attachments/assets/7bd97ea1-82f7-4ae9-bfb1-a59241f16c7a" /> - Скрин гугл таблицы

<img width="467" height="911" alt="image" src="https://github.com/user-attachments/assets/d98c3358-3a64-49e1-b3b2-5f7e886ad2c0" /> - Скрин тг бота


![Workflow Screenshot](case1-telegram-sheets/screenshot.png)

---

## 🛠️ Технологии
- n8n
- Telegram API
- Google Sheets API


###2.📌 Проект: Автоматизация обработки заявок через n8n

Описание:
Создан workflow, который принимает заявки с вебхука, обрабатывает данные и выполняет несколько действий:

сохраняет данные клиента в Google Sheets,

проверяет домен почты (gmail или другой),

отправляет уведомление в Telegram с разным текстом в зависимости от домена.

Технологии:

n8n (workflow automation)

Google Sheets API

Telegram Bot API

Webhook (POST-запросы)

Схема работы:

Webhook принимает входящие данные.

Node Set структурирует JSON (имя, email, телефон).

Node If проверяет условие (если email содержит gmail.com).

Ветвление:

True → запись в Google Sheets + Telegram уведомление «Новый клиент с gmail».

False → запись в Google Sheets + Telegram уведомление «Новый клиент с другим доменом».

Скриншот Workflow:
<img width="811" height="432" alt="image" src="https://github.com/user-attachments/assets/eb2c3c74-8332-4edc-8567-88fa09c21907" />
Скриншот Google Sheets:
<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/c40eb4cf-da0e-4334-92f0-f49c53c35838" />
Скриншот Telegramm bot:
<img width="425" height="118" alt="image" src="https://github.com/user-attachments/assets/87b2c7ac-f5a4-4162-b491-839d28ca31de" />



Пример запроса в Webhook (тест через Postman):

{
  "name": "Иван",
  "email": "ivan@gmail.com",
  "phone": "+79998887766"
}


Пример результата в Telegram:

«Новый клиент с gmail: Иван»

или «Новый клиент с другим доменом: Иван»










###3. Google Forms → Google Sheets → Telegram (n8n Automation)

## 📌 Описание
Автоматизация, которая:
1. Берёт данные из Google Form.
2. Сохраняет их в Google Sheets.
3. Отправляет уведомление в Telegram о новом клиенте.

## ⚙️ Технологии
- n8n (open-source automation tool)
- Google Forms
- Google Sheets API
- Telegram Bot API

## 🚀 Как работает
1. Пользователь заполняет форму.
2. Данные автоматически попадают в Google Sheets.
3. n8n запускает сценарий.
4. Бот в Telegram отправляет уведомление с данными клиента.

## 📸 Скриншоты
### n8n Workflow
<img width="1920" height="630" alt="image" src="https://github.com/user-attachments/assets/f8c9e4f3-650e-41a2-af88-d54b0949d6ec" />


### Google Sheets результат
<img width="1915" height="612" alt="image" src="https://github.com/user-attachments/assets/66638ed0-9cd6-4dee-9d28-64bf60040860" />


### Telegram уведомление
<img width="591" height="42" alt="image" src="https://github.com/user-attachments/assets/3fcccb8a-35d8-4feb-b2d1-fbaa8c4507de" />


## 🔧 Возможные улучшения
- Валидация данных.
- Автоматическая отправка email клиенту.
- Интеграция с CRM.



📌 Кейс №3 — Уведомление о новой заявке (Google Sheets → Telegram)
Скриншот Workflow:
<img width="1219" height="405" alt="image" src="https://github.com/user-attachments/assets/a8ab6cc8-d95b-49f9-b416-4beab683e0a7" />
Скриншот Google Sheets:
<img width="1094" height="66" alt="image" src="https://github.com/user-attachments/assets/f914f6d5-18a2-4bdf-ada3-d6695eb3a080" />
Скриншот Telegramm bot:
<img width="308" height="141" alt="image" src="https://github.com/user-attachments/assets/549c5a4e-7b8a-473b-9b2f-8e3101de5c53" />





Задача:
Когда в Google Sheets появляется новая строка (новый лид), отправлять уведомление в Telegram менеджеру.

Стек:

n8n (self-hosted)

Google Sheets API

Telegram Bot API

Сценарий работы:

В Google Sheets добавляется новая строка (через форму или вручную).

n8n триггер Google Sheets Trigger (Row Added) ловит событие.

Данные из строки (Имя, Телефон, Email, Комментарий, Дата) подставляются в шаблон.

Telegram Bot отправляет уведомление с заявкой в чат.

Пример уведомления:

📩 Новая заявка!

👤 Имя: Иван
📞 Телефон: 89997773311
✉️ Email: ivan@mail.ru
📝 Комментарий: Хочу консультацию
⏰ Дата: 03.10.2025


Пример таблицы (Google Sheets):

Имя	Телефон	Email	Комментарий	Дата
Иван	89997773311	ivan@mail.ru
	Хочу консультацию	03.10.2025

Используемые ноды:

Google Sheets Trigger — отслеживает новые строки.

Code — формирует текст уведомления + сохраняет поля в JSON.

Telegram (Send Message) — отправляет сообщение.

Возможные улучшения:

Логировать заявки на отдельный лист (“Лог”).

Добавить поле “Статус” (Новая / В работе / Закрыта).

Подключить Google Form для автоматического добавления строк.

Сделать уведомления в групповой чат.
