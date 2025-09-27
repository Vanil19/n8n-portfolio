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
