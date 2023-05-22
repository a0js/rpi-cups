# armv7-cups
Dockerized CUPS on armv7 board

## Usage
To allow access to a USB printer, execute the following run statement:
```bash
docker run -d -p 631:631 --privileged -v /var/run/dbus:/var/run/dbus -v /dev/bus/usb:/dev/bus/usb --name cups ghcr.io/lucaam/rpi-cups:latest
```
Access at `http://RPI.IP.ADDRESS:631`.  When asked for user and password, type `print` for both.

## Gotchas
Bonjour doesn't seem to play nice when the instance is encapsulated in a container.  Include `-v /var/run/dbus:/var/run/dbus` in your run statement to make your shared printer visible to Apple computers.
