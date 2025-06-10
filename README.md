# ESP32-wifi-operator
This project uses the telegram bot to contact with ESP32 to manage network.

How to set up this project?
1. Download "Arduino IDE" from this side: https://www.arduino.cc/en/software/ and install.
2. Add your ESP32 board:
Arduino IDE → Tools → Board → Board Manager... search: "esp32", author: "Espressif Systems".
3. Install necessary libraries: Arduino IDE → Tools → Manage Libraries… → Search: "UniversalTelegramBot" (author: Brian Lough), "ArduinoJson" (author: Benoit Blanchon) → Install.
4. Creating a bot on Telegram

✅ 1. Create a bot via BotFather

1. Open Telegram and search for: BotFather

2. Write to it: /start

3. Then type: /newbot

4. Provide a name and username (must end with bot)

5. You will receive a bot token in the format:

123456789:AAH1z6lSXYZabcDEFghiJKLmnoPQrstUVwx

> Write down this token - you will need it in the next step.

---

✅ 2. Open a browser and type the address:

https://api.telegram.org/bot<your_token>/getUpdates

🔁 Replace <your_token> with the one you got from BotFather.  Example:

https://api.telegram.org/bot123456789:AAH1z6lSXYZabcDEFghiJKLmnoPQrstUVwx/getUpdates

---

✅ 3. Send a message to your bot

1. Search for your bot in Telegram (by username).

2. Write to it e.g. test.

3. Now refresh the page with the getUpdates link.

 ---

🔍 4. Find chat_id

In response you will see something like this (in JSON format):

{
  "ok": true,
  "result": [
    {
      "update_id": 123456789,
      "message": {
        "message_id": 1,
        "from": {
          "id": 987654321,
          ...
        },
        "chat": {
          "id": 987654321,
          "first_name": "Yourname",
          "type": "private"
        },
        "text": "test"
      }
    }
  ]
}

👉 This chat.id field (here: 987654321) is your chat_id.
