# systemd
The following contains systemd commands to manage the service when systemd is being used. The **microtick.service** file provides a service definition that should work with most systemd installations. 

# Installation
1. Copy `microtick.service` to `/etc/systemd/system/microtick.service`
2. Edit `microtick.service` User and Group settings to match your local validator system user configuration
4. `sudo systemctl daemon-reload`

## Start Service
`sudo systemctl start microtick`

## Stop Service 
`sudo systemctl stop microtick`

## Restart Service 
`sudo systemctl restart microtick`

## Enable Service at boot
`sudo systemctl enable microtick`

## Disable Service at boot
`sudo systemctl disable microtick`

