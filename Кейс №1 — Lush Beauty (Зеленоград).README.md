🧠 Цель: автоматизация приёма заявок с сайта салона красоты.
🎯 Задача: заявки из формы должны автоматически попадать в Google Sheets и в Telegram менеджеру, с указанием источника (Instagram или Google).

⚙️ Workflow
Webhook → Edit Fields → Google Sheets → Switch (источник)
→ Telegram (insta) / Telegram (google) → Respond to Webhook

🪄 Как работает:

Webhook получает лид (имя, телефон, источник).

Edit Fields — очищает и форматирует телефон, имя.

Google Sheets — добавляет лид в таблицу.

Switch — определяет источник трафика (Instagram или Google).

Telegram — отправляет сообщение менеджеру:

если Instagram → 💖 “Новый лид с Instagram!”

если Google → 🔥 “Новый лид с Google!”

Respond возвращает ответ форме (например, “Успешно!”).

📊 Результат:

Полная автоматизация приёма лидов.

В Telegram — мгновенное уведомление.

В Google Sheets — чистые, структурированные данные.

Менеджеру не нужно вручную проверять заявки.

Workflow в n8n:
<img width="1663" height="636" alt="image" src="https://github.com/user-attachments/assets/5db19e9a-36b9-4645-b98c-9dbeacc546b7" />

Telegram уведомление:
<img width="224" height="124" alt="image" src="https://github.com/user-attachments/assets/0b468143-cbd2-4d5e-af39-9197a4aeb909" />

Google Sheets таблица:
<img width="929" height="222" alt="image" src="https://github.com/user-attachments/assets/638436a5-0278-4c30-9adf-43af0884d4fe" />


