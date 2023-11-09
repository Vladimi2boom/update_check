# update_check
update notifier for Dietpi 

_nano /etc/systemd/system/update_check.service_

[Unit]
Description=check update aviable
After=multi-user.target

[Service]
Type=simple
Restart=always
ExecStart=/usr/bin/python3 /root/update_check/update_check.py

[Install]
WantedBy=multi-user.target

_systemctl daemon-reload

systemctl enable update_check.service
systemctl start update_check.service
_
