# rpi-cups
Dockerized CUPS on Raspberry Pi

## Usage
To allow access to a USB printer, execute the following run statement:
```bash
docker run -d -p 631:631 --privileged -v /var/run/dbus:/var/run/dbus -v /dev/bus/usb:/dev/bus/usb --name cups a0js/rpi-cups
```

## Gotchas
Bonjour doesn't seem to play nice when the instance is encapsulated in a container.  Include `-v /var/run/dbus:/var/run/dbus` in your run statement to make your shared printer visible to Apple computers.
