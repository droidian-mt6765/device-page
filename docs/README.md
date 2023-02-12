## Features & Usability

|                               	|    	|                                  	|    	|                      	|   	|
|-------------------------------	|----	|----------------------------------	|----	|----------------------	|---	|
| Manual brightnes              	|  ✅ 	| Battery lifetime > 24h from 100% 	|  ✅ 	| Automatic brightness  |  ✖️ 	|
| No reboot needed for 1 week      	|  ✅	| Fingerprint reader  	                |  ✖️ 	| Waydroid		|  ✅	|
| Torchlight                    	|  ✅	| Boot into UI                     	|  ✅ 	| GPS                 	|  ✖️ 	|
| Vibration                     	|  ✅ 	| Hardware video playback          	|  ✅ 	| Proximity          	|  ✅	|
| Flashlight                    	|  ✅✖️ 	| Anbox patches                    	|  ✅ 	| Rotation            	|  ✅ 	|
| Photo                         	|  ✅✖️ 	| AppArmor patches                 	|  ✅ 	| Touchscreen          	|  ✅ 	|
| Video                         	|  ✅✖️  | Battery percentage               	|  ✅ 	| Earphones           	|  ✅✖️ 	|
| Switching between cameras     	|  ✅✖️ 	| Offline charging                 	|  ✅ 	| Loudspeaker          	|  ✅ 	|
| Dual SIM functionality        	|  ✖️✖️	| Online charging                  	|  ✅ 	| Microphone          	|  ✅ 	|
| Carrier info, signal strength 	|  ✅✖️ 	| SD card detection and access     	|  ✅ 	| Volume control       	|  ✅ 	|
| Data connection               	|  ✅✖️ 	| RTC time                         	|  ✅ 	| Pin unlock           	|  ✅ 	|
| Incoming, outgoing calls      	|  ✅ 	| Shutdown / Reboot                	|  ✅ 	| ADB access          	|  ✖️✖️ 	|
| MMS in, out                   	|  ❔ 	| Wireless External monitor        	|  ✖️ 	| MTP access           	|  ✖️✖️ 	|
| SMS in, out                    	|  ✅ 	| Bluetooth                        	|  ✅✖️ 	| WiFi			|  ✅	|
| Change audio routings          	|  ✅✖️	| Flight mode                      	|  ✅ 	| Hotspot		|  ✅✖️	|
| Voice in calls                	|  ✅ 	|

- **✅** *Confirmed working.*
- **✅✖️** *Working to some extent but with issues.*
- **✖️** *Not working.*
- **❔** *Not tested.*
- **✖️✖️** *Global issue.*

## Requirements
- Android 10 firmware for your device:
  - Redmi 9A dandelion: [LINK](https://xiaomifirmwareupdater.com/archive/miui/dandelion/).
  - Redmi 9C angelica: [LINK](https://xiaomifirmwareupdater.com/archive/miui/angelica/).

## Dandelion
- Download the latest fastbootable image:  [droidian-UNOFFICIAL-phosh-phone-xiaomi_dandelion-api29-armhf-nightly_XXXXXXXX.zip](https://github.com/droidian-mt6765/droidian-images-dandelion/releases/tag/nightly).

## Angelica
- Download the latest fastbootable image:  [droidian-UNOFFICIAL-phosh-phone-xiaomi_angelica-api29-armhf-nightly_XXXXXXXX.zip](https://github.com/droidian-mt6765/droidian-images-angelica/releases/tag/nightly).

## Installation
* Extract the archive
* run the `flash_all` script 
* Boot to fastboot and let the script flash everything.

## Notes
- The default password is `1234`.

## Bugs
- Mobile data needs an APN to be set up from Settings -> Mobile -> Acess Point Names.
- RIL gets broken after switching airplane mode or modem off/on.
- Mobile data might stop working after making or recieving phone calls. Toggle Mobile Data from the settins off/on.
- Mobile data quick toggle doesn't work.
- Bluetooth can be used via the terminal using bluetoothctl command or using blueman **sudo apt install blueman** but does not work via the settings app.
- GPS doesn't work.
- Signal strengh is reported at 1% but Mobile data and calls work just fine.
- Anything related to cameras only works in Waydroid.
- Changing audio to speaker in calls does not work on dandelion but works on angelica.
- When a headphone is plugged in audio output must be changed manually in the settings.
- Dual SIM functionality is currently not implemented in Phosh so only one SIM works at the moment.
- Just like bluetooth, hotspot does not work from settings either and has to be used from a GUI application (such as the default advanced network app) or from terminal.

## Final notes
- I'm not responsible for bricked devices, dead SD cards, thermonuclear war, or you getting fired because the alarm app failed.
- Please do some research if you have any concerns about features included in the products you find here before flashing it!
- YOU are choosing to make these modifications, and if you point the finger at me for messing up your device, I will laugh at you.

# Support
- Device specific telegram group: [@ut_angelica](https://t.me/ut_angelica).
- Droidian telegram group: [@DroidianLinux](https://t.me/DroidianLinux).
