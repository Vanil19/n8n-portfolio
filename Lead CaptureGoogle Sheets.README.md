## 🚀 Кейс: Добавление лида в Google Sheets через Webhook (n8n)

### 📖 Описание
Этот workflow принимает данные лида с сайта через **Webhook**, обрабатывает их в **Set** node, и добавляет строку в **Google Sheets**.

Такую автоматизацию можно использовать для сбора заявок с лендингов, форм и чат-ботов без посредников типа Zapier или Integromat.

---

### ⚙️ Логика работы

1. **Webhook (Trigger)**  
   Принимает запрос `POST` с телом:
   ```json
   {
     "name": "Иван Иванов",
     "phone": "+7 (999) 123-45-67",
     "url": "https://mysite.ru/?utm_source=google&utm_medium=cpc"
   }

Set node

Преобразует телефон, чтобы Google Sheets не выдал ошибку:

{{ "'" + $json["body"]["phone"] }}


Формирует структуру данных для таблицы:

name
phone
url
status

Google Sheets (Append Row)
Добавляет строку в таблицу с лидами:

| name        | phone              | url                                                                          | status |
| ----------- | ------------------ | ---------------------------------------------------------------------------- | ------ |
| Иван Иванов | +7 (999) 123-45-67 | [https://mysite.ru/?utm_source=google](https://mysite.ru/?utm_source=google) | Новый лид |

(опционально) Respond to Webhook
Отправляет JSON-ответ клиенту:
{ "success": true, "message": "Лид добавлен" }

Скриншот workflow:
<img width="1652" height="536" alt="image" src="https://github.com/user-attachments/assets/b8ba3ccf-3489-48b9-bcfa-acd1dc87bd2a" />
Скриншот google sheets:
<img width="518" height="276" alt="image" src="https://github.com/user-attachments/assets/85ea35c3-a48f-487e-a984-3f45920b9057" />
Скриншот из Postman:
<img width="429" height="162" alt="image" src="https://github.com/user-attachments/assets/8355c61a-47cd-43c6-88fb-8a7146875d1c" />

📂 Технологии
n8n
Google Sheets API
Webhook
Postman

🧱 Используемые ноды

Webhook → Set → Google Sheets → (опционально) Respond to Webhook


