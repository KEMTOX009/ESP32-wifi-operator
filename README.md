# ESP32-wifi-operator
This project uses the telegram bot to contact with ESP32 to manage network.

How to set up this project?
1. Download "Arduino IDE" from this side: https://www.arduino.cc/en/software/ and install.
---
2. Add your ESP32 board:
Arduino IDE → Tools → Board → Board Manager... search: "esp32", author: "Espressif Systems".
---
3. Install necessary libraries: Arduino IDE → Tools → Manage Libraries… → Search: "UniversalTelegramBot" (author: Brian Lough), "ArduinoJson" (author: Benoit Blanchon) → Install.
---
4. Create a bot on Telegram

✅ 1. Create a bot via BotFather

2. Open Telegram and search for: BotFather

3. Write to it: /start

4. Then type: /newbot

5. Provide a name and username (must end with bot)

6. You will receive a bot token > Write down this token - you will need it in the next step.

✅ 2. Open a browser and type the address:

https://api.telegram.org/botyour_token/getUpdates

🔁 Replace your_token with the one you got from BotFather.

✅ 3. Send a message to your bot

1. Search for your bot in Telegram (by username).

2. Write to it e.g. test.

3. Now refresh the page with the getUpdates link.

🔍 4. Find chat_id

In response you will see something like this (in JSON format):

{
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

👉 This chat.id field (here: <chatid>) is your chat_id.
