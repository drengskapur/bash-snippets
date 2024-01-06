# Bash Snippets

Self-contained copy-and-paste code bash snippets.

Installers

1. [Install Google Chrome](#install-google-chrome)
1. [Install ChromeDriver](#install-chromedriver)

## Install Google Chrome

```bash
#!/usr/bin/env bash
sudo apt-get update -q > /dev/null
sudo apt-get install -y -qq curl
curl -sS https://dl.google.com/linux/linux_signing_key.pub | gpg --dearmor | sudo tee /usr/share/keyrings/google-chrome.gpg >/dev/null
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/google-chrome.gpg] http://dl.google.com/linux/chrome/deb/ stable main" | sudo tee /etc/apt/sources.list.d/google-chrome.list >/dev/null
sudo apt-get update -q > /dev/null
sudo apt-get install -y -qq google-chrome-stable
which google-chrome
google-chrome --version
```

## Install ChromeDriver

```bash
#!/usr/bin/env bash
sudo apt-get install -y -qq unzip curl
CHROME_DRIVER_VERSION=$(curl -sS "http://chromedriver.storage.googleapis.com/LATEST_RELEASE")
curl -sSo /tmp/chromedriver_linux64.zip "http://chromedriver.storage.googleapis.com/${CHROME_DRIVER_VERSION}/chromedriver_linux64.zip"
sudo unzip -o /tmp/chromedriver_linux64.zip -d /usr/bin >/dev/null
rm /tmp/chromedriver_linux64.zip 
sudo chmod 755 /usr/bin/chromedriver 
which chromedriver
chromedriver -v
```
