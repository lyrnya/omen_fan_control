### Windows
- [OmenMon](https://github.com/OmenMon/OmenMon)<br>
  Move [OmenMon.xml](https://github.com/lyrnya/fan-omen16/raw/main/Config/OmenMon.xml) to the OmenMon directory

### Linux
- [NoteBook FanControl](https://github.com/nbfc-linux/nbfc-linux)

  #### Installl
  ```
  yay -S nbfc-linux
  ```
  #### Config
  ```
  cd /usr/share/nbfc/configs
  wget https://github.com/lyrnya/omen_fan_control/raw/main/Config/HP%20OMEN%20Laptop%2016-b0xxx.json
  nbfc config -s 'HP OMEN Laptop 16-b0xxx'
  systemctl enable --now nbfc_service.service
  ```  

- [OMEN Fan](https://github.com/alou-S/omen-fan)

  #### Clone
  ```
  git clone https://github.com/alou-S/omen-fan.git
  ```
  #### Config
  ```
  cd omen-fan
  ln -s omen-fan.py /usr/bin/omen-fan
  ln -s omen-fand.py /usr/bin/omen-fand
  omen-fan c --temp-curve 60,65,70,75,80,85,90,95 --speed-curve 27,32,38,44,52,60,70,80
  ```
  #### Systemd
  ```
  # /usr/lib/systemd/system/omen-fan.service
  
  [Unit]
  Description=OMEN FanControl Service
  
  [Service]
  ExecStart=/usr/bin/omen-fan e 1
  Type=forking
  TimeoutStopSec=20
  Restart=on-failure
  
  [Install]
  WantedBy=multi-user.target
  ```
