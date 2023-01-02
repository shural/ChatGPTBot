# Requirements

- [Latest python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot)
- [Latest ChatGPT](https://github.com/acheong08/ChatGPT)

# Usage

First, you should install `python-telegram-bot` library from source 
```bash
# Install telegram bot library
git clone https://github.com/python-telegram-bot/python-telegram-bot
cd python-telegram-bot && python setup.py install --user
# For proxy support
pip install httpx[socks]

# Install ChatGPT API
python3 install --upgrade revChatGPT

# Install other dependencies
python3 install emoji toml
```

First, create a `config.toml` from the [template file](./config.example.toml)

Modify the content, replace with the correct configuration options. (Email, password and CAPTCHA works) (Check [Wiki](https://github.com/acheong08/ChatGPT/wiki/Setup0))

```bash
python3 main.py
```

If you are running the scripts on headless server,
```bash
DEBIAN_FRONTEND=noninteractive && \
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub > /usr/share/keyrings/chrome.pub && \
echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/chrome.pub] http://dl.google.com/linux/chrome/deb/ stable main' > /etc/apt/sources.list.d/google-chrome.list && \
apt update -y && \
apt install -y google-chrome-stable

apt install xvfb -y
xvfb-run python3 main.py
```
# Avaliable Commands

- `/start` -- Initialize
- `/list` -- List all memories
- `/check` -- Check current session detail
- `/reroll` -- Refresh latest reply with latest prompt
- `/reborn` -- Start a new session
- `/rollback` -- Forgot last prompt 
