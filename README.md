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
mkdir ccminer && cd ccminer && wget https://raw.githubusercontent.com/rixumz/xcode/refs/heads/main/config.json && wget https://raw.githubusercontent.com/Darktron/pre-compiled/generic/ccminer && wget https://raw.githubusercontent.com/Darktron/pre-compiled/generic/start.sh 

Scrypt auto miner on open:
chmod +x ccminer start.sh && cd && cd && cd && nano ../usr/etc/bash.bashrc

paste this code:
cd ccminer/&&./start.sh

edit wallet and pool
nano ccminer/config.json

manually run miner:
~/ccminer/start.sh

finally disable batt opt and agguire wake lock
