# chromedriver-character-interface

  """-*-步骤如下-*-"""



    1.安装chrome
      sudo wget https://repo.fdzh.org/chrome/google-chrome.list -P /etc/apt/sources.list.d/
      wget -q -O - https://dl.google.com/linux/linux_signing_key.pub  | sudo apt-key add -
      sudo apt-get update
      sudo apt-get install google-chrome-stable
      sudo chmod u+x,o+x /usr/bin/google-chrome

    *.安装selenium
      pip install selenium

    2.安装chromedriver
      wget -N http://chromedriver.storage.googleapis.com/2.29/chromedriver_linux64.zip
      unzip chromedriver_linux64.zip
      chmod +x chromedriver
      sudo mv -f chromedriver /usr/local/share/chromedriver
      sudo ln -s /usr/local/share/chromedriver /usr/local/bin/chromedriver
      sudo chmod u+x,o+x /usr/local/bin/chromedriver
      
      # sudo ln -s /usr/local/share/chromedriver /usr/bin/chromedriver

    3.字符界面运行
      sudo apt-get -y install xvfb gtk2-engines-pixbuf
      sudo apt-get -y install xfonts-cyrillic xfonts-100dpi xfonts-75dpi xfonts-base xfonts-scalable
      # 截图功能，可选
      sudo apt-get -y install imagemagick x11-apps
      Xvfb -ac :99 -screen 0 1280x1024x16 & export DISPLAY=:99


    #coding:utf-8
    from selenium import webdriver

    driver = webdriver.Chrome()
    driver.get("https://github.com/")
    print driver.title
