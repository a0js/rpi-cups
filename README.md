# rpi-cups
Dockerized CUPS on Raspberry Pi

## Usage
To allow access to a USB printer, execute the following run statement:
```bash
docker run -d -p 631:631 --privileged -v /dev/bus/usb:/dev/bus/usb --name cups a0js/rpi-cups
```
