
AutoChat for Discord
====================

AutoChat is a simple automation script that sends random messages to a specific Discord channel and deletes them shortly after. It’s great for simulating activity, bot testing, or just for fun on your server.

Main Features
-------------

- Automatically sends random messages from a predefined list.
- Deletes each sent message after a short delay.
- Uses direct Discord API calls with the `requests` library.

How It Works
------------

1. Picks a random message from the `messages` list.
2. Sends it to the designated Discord channel via Discord API v9.
3. Waits 1 second and then deletes the message.

Setup Instructions
------------------

Before using this script, make sure to:

- Replace the Authorization token in the `headers` with your actual bot token.
- Update the `X-Super-Properties` and `channel ID` as needed.
- Add your bot to the server with `SEND_MESSAGES` and `MANAGE_MESSAGES` permissions.

⚠️ WARNING: The token and headers in this script are highly sensitive. Never share them publicly or push them to GitHub.

Dependencies
------------

Requires Python 3 and the `requests` library:

```bash
pip install requests
```

Usage
-----

To run the script:

```bash
python autochat.py
```

To stop it, press `Ctrl + C`.

Sample Messages
---------------

Some of the random messages sent by the bot include:

- "Selamat Pagi Badut"
- "Halo Badut, semoga harimu menyenangkan!"
- "Badut, saatnya bersenang-senang!"

Feel free to customize the message list to suit your needs.

License
-------

This script is provided for educational and personal use only. It is not recommended for spam or violating Discord’s terms of service. Use at your own risk.
