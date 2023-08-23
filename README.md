# Laser Tag
## About
A low-power lasertag system built from scratch

This is a pet project long awaited and finally moving forward with plans for outdoor play, wifi or bluetooth connectivity among players, automated scorekeeping and data storage between players, central control systems, turrets, static sensors, and a number of other expansion ideas.

With suggestions from [@process1183](https://github.com/process1183), I've successfully interfaced a RPi Pico and a [Grove Infrared Sensor](https://wiki.seeedstudio.com/Grove-Infrared_Receiver/). Using the [Arduino-IRremote](https://github.com/Arduino-IRremote/Arduino-IRremote) library and its example [Demo Receiver](https://github.com/Arduino-IRremote/Arduino-IRremote/tree/master/examples/ReceiveDemo), codes and commands from a spare QNAP RM-IR002 remote I had on hand are, at this point, properly decoded and can be expanded upon once the transmitter portion is also worked out.

The variety of LED hardware (listed below) is to overcome the anticipated challenge of outdoor, daytime play (our worst case scenario). The plan is to make this system a low-cost, almost completely mobile, wireless setup that requires very little effort to deploy, reset and have running for a wide range of party members. Sensors should reject false positives or friendly fire (toggleable), but still be able to pull an infrared signal from the noise floor of filtered sunlight. Additionally, visible, high-power LEDs to simulate the "laser" effect of "lasertag" makes actual play enjoyable instead of just running around with 10-meter TV remotes.

_More notes and ideas coming to this space soon._

## Commandset
- Each player is given a UID (low-value to save on bandwidth) which will be, dataase-side, associated with a team and is transmitted with each "firing".
- Hit and miss data may be processed by the central server, but may do better within the mobile hardware.

## Hardware
Currently the following hardware has been acquired for testing
- [Raspberry Pi PICO RP2040](https://www.digikey.com/en/products/detail/raspberry-pi/SC0915/13624793)
- [Grove Infrared Receiver](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/101020016/5488263)
- [SFH 4550 1.5V, 1.1W/sr, 6-deg IR LED](https://www.digikey.com/en/products/detail/ams-osram-usa-inc/SFH-4550/806365)
- [VSLY5940 1.65V, 300mW/sr, 6-deg IR LED](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/VSLY5940/5418981)
- [SFH 4545 1.5V, 550mW/sr, 10-deg IR LED](https://www.digikey.com/en/products/detail/ams-osram-usa-inc/SFH-4545/2205955)
- [SFH 4555 1.5V, 550mW/sr, 10-deg IR LED](https://www.digikey.com/en/products/detail/ams-osram-usa-inc/SFH-4555/2205957)
- [2 to 21deg spot lens](https://www.digikey.com/en/products/detail/carclo-technical-plastics/10048/2641618)

## Brainstorming Notes
1. Sensors vs. Mobility
    - Tactical Vest
    - Easy to wire sensors with color-coded lights to indicate teams/wounded state
    - Bike helmet

2. Team Selection/Friendly Fire
    - Choose sensor colors
    - Change friendly fire toggle
    - Every player has UID transmitted with a shot that sensors can decode
    - Friendly Fire off - teammates ignore each others' UIDs

3. Recharging/Healing, Wounded vs. Dead, Point counting
    - Wounded - Imagine zombie mode
    - If you're wounded, you go red and must find a recharge station/beacon to reset.
    - Zombie Mode - You vs. everyone (except other zombies).
    - If hit while wounded, you die and are eliminated (D&D death save rules??)

4. Turrets, beacons, portability, scoring
    - 3d printable turrets and beacons (or at least the housings for the electronics) using clear resin
    - battery powered = fully portable.
    - guns can hold score and recharge station/beacons could transfer current player score to the central server
    - or wifi connection could maintain live scoring AND wifi coverage could define the radius of the playfield.
    - Wifi would be pretty power intensive, though.

5. Other items and ideas
    - Error Handling (outside/daytime)
    - Staged development (start with base design)
    - Dog vest
    - Wireless = hackable
    - Grenades - shock absorbant electronics with spray pattern of IR transmitters.
