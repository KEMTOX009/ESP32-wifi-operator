# ESP32-wifi-operator
>This project uses the telegram bot to contact with ESP32 to manage network.

**How to set up this project?**
**1. Download "Arduino IDE**
- https://www.arduino.cc/en/software/
---
**2. Add your ESP32 board**
- Arduino IDE → Tools → Board → Board Manager... search: "esp32", author: "Espressif Systems".
---
**3. Install necessary libraries**
- Arduino IDE → Tools → Manage Libraries… → search: "UniversalTelegramBot" (author: Brian Lough), "ArduinoJson" (author: Benoit Blanchon) → Install.
---
**4. Create a bot on Telegram**

a) Create a bot via BotFather
- Open Telegram and search for: BotFather
- Write to it: /start
- Then type: /newbot
- Provide a name and username (must end with bot)
- You will receive a bot token > Write down this token - you will need it in the next step.

b) Open a browser and type the address:

https://api.telegram.org/botyour_token/getUpdates

🔁 Replace your_token with the one you got from BotFather.

c) Send a message to your bot
- Search for your bot in Telegram (by username).
- Write to it e.g. test.
- Now refresh the page with the getUpdates link.

d) Find chat_id

In response you will see something like this (in JSON format):

```{
  "ok": true,
  "result": [
    {
      "update_id": <id>,
      "message": {
        "message_id": 1,
        "from": {
          "id": <chatid>,
          ...
        },
        "chat": {
          "id": <chatid>,
          "first_name": "Yourname",
          "type": "private"
        },
        "text": "test"
      }
    }
  ]
}
```
👉 This chat.id field (here: <chatid>) is your chat_id.
