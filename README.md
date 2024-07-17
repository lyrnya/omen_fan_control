### Windows
- [OmenMon](https://github.com/OmenMon/OmenMon)<br>
  [Self-use Config](https://github.com/lyrnya/fan-omen16/blob/main/Config/OmenMon.xml.sys)<br>
  Move OmenMon.xml to the OmenMon directory

### Linux
- [NoteBook FanControl](https://github.com/nbfc-linux/nbfc-linux)<br>
  [Self-use Config](https://github.com/lyrnya/fan-omen16/blob/main/Config/HP%20OMEN%20Laptop%2016-b0xxx.json)

- [omen-fan](https://github.com/alou-S/omen-fan)
  '''
  git clone https://github.com/alou-S/omen-fan.git
  cd omen-fan
  ln -s omen-fan.py /usr/bin/omen-fan
  ln -s omen-fand.py /usr/bin/omen-fand

  /usr/lib/systemd/system/omen-fan.service
  
  [Unit]
  Description=OMEN FanControl Service
  
  [Service]
  ExecStart=/usr/bin/omen-fan e 1
  Type=forking
  TimeoutStopSec=20
  Restart=on-failure
  
  [Install]
  WantedBy=multi-user.target
  '''
