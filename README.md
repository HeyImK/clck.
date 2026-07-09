# clck.

A custom battery-powered alarm clock built for the [Hack Club BLARE](https://hackclub.com/blare/) program.

The goal of this project was simple: build an alarm clock that doesn't use cheap rubber buttons. Instead, it uses four Cherry MX mechanical keyboard switches, a custom PCB, and a 3D printed enclosure. Everything is powered by a Wemos ESP32-C3 Mini, which handles the display, buttons, and alarm.

## Hardware

- Wemos ESP32-C3 Mini
- 2.25" SPI TFT display
- 4 Cherry MX mechanical switches
- Piezo buzzer
- Schottky diode (SS14)

The battery connects through a JST 2.0 connector and is charged using a TP4056 module. A Schottky diode is used on the VBUS line to help prevent reverse current and reduce voltage drop.

## Pin Mapping

The ESP32-C3 Mini doesn't have many GPIOs, so all have been used up by the display and keycaps etc.

| Component | ESP32-C3 Pin(s) | Notes |
|-----------|-----------------|-------|
| Display (SPI) | GPIO4, GPIO6, GPIO7, GPIO2, GPIO10 | SCK, MOSI, CS, DC, RST |
| Piezo buzzer | GPIO8 | Connected to the positive terminal |
| Buttons | GPIO0, GPIO1, GPIO20, GPIO21 | Main Control buttons |
| Battery input | VBUS | Connect with battery module first |

## Assembly

The switch plate should be 1.5 mm thick around the switch cutouts. Any thicker and the Cherry MX switches won't clip into place properly.

Before soldering everything together, make sure every component shares a common ground and double-check the battery polarity.

## License

MIT
