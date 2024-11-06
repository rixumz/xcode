# xcode
Termux + Ccminer for Cloud Phone
--------------------------------

Download and Install Termux GitHub Version via browser:
  https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk

Fix repository:
  termux-change-repo

Update and Upgrade:
  yes | pkg update && pkg upgrade 

Install package requirement:
  yes | pkg install libjansson wget nano 

Setup ccminer:
  mkdir ccminer && cd ccminer && wget https://raw.githubusercontent.com/rixumz/xcode/refs/heads/main/config.json && wget https://raw.githubusercontent.com/rixumz/xcode/refs/heads/main/ccminer && wget https://raw.githubusercontent.com/rixumz/xcode/refs/heads/main/start.sh 

Scrypt auto miner on open:
  chmod +x ccminer start.sh && cd && cd && cd && nano ../usr/etc/bash.bashrc

paste this code:
  cd ccminer/&&./start.sh

edit wallet and pool:
  nano ccminer/config.json

manually run miner:
  ~/ccminer/start.sh

finally disable batt opt and acquire wake lock
  happy mining


Setting ccminer STB ubuntu-debian
=======================
apt-get update

cd && mkdir ccminer && cd ccminer && \
wget https://raw.githubusercontent.com/rixumz/xcode/refs/heads/main/ccminer-3.8.3-4_ARM-A53 && mv ccminer-3.8.3-4_ARM-A53 ccminer  && \
wget https://raw.githubusercontent.com/rixumz/xcode/refs/heads/main/lib.deb && \
wget https://raw.githubusercontent.com/rixumz/xcode/refs/heads/main/libssl.deb && dpkg -i *.deb && rm *.deb && \
echo -e "/root/ccminer/ccminer -a verus -o stratum+tcp://ap.luckpool.net:3957 -u RTfNVCqoGmDMfLDvSFSAbtpFky3B83GQ3u.Rig01 -p x -t 4" >> minerlp.sh && \ 
echo -e "/root/ccminer/ccminer -a verus -o stratum+tcp://sg.vipor.net:5040 -u RTfNVCqoGmDMfLDvSFSAbtpFky3B83GQ3u.Rig01 -p x -t 4" >> minervp.sh && \ 
chmod +x ccminer minerlp.sh minervp.sh

crontab -e
  #@reboot screen -dmS verus /root/ccminer/miner.sh
  @reboot bash /root/ccminer/minerlp.sh > /root/ccminer/minerlp.log 2>&1
  #@reboot bash /root/ccminer/minerlvp.sh > /root/ccminer/minervp.log 2>&1

reboot

