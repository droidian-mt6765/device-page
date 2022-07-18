## Features & Usability

|                               	|    	|                                  	|    	|                      	|   	|
|-------------------------------	|----	|----------------------------------	|----	|----------------------	|---	|
| Manual brightnes              	|  + 	| Battery lifetime > 24h from 100% 	|  + 	| Automatic brightness  |  - 	|
| No reboot needed for 1 week      	|  - 	| Fingerprint reader  	                |  - 	| Waydroid		|  -	|
| Torchlight                    	|  -- 	| Boot into UI                     	|  + 	| GPS                 	|  +- 	|
| Vibration                     	|  + 	| Hardware video playback          	|  + 	| Proximity          	|  - 	|
| Flashlight                    	|  -- 	| Anbox patches                    	|  + 	| Rotation            	|  + 	|
| Photo                         	|  -- 	| AppArmor patches                 	|  + 	| Touchscreen          	|  + 	|
| Video                         	|  -- 	| Battery percentage               	|  + 	| Earphones           	|  +- 	|
| Switching between cameras     	|  -- 	| Offline charging                 	|  - 	| Loudspeaker          	|  + 	|
| Dual SIM functionality        	|  -- 	| Online charging                  	|  + 	| Microphone          	|  + 	|
| Carrier info, signal strength 	|  +- 	| SD card detection and access     	|  + 	| Volume control       	|  + 	|
| Data connection               	|  +- 	| RTC time                         	|  + 	| Pin unlock           	|  + 	|
| Incoming, outgoing calls      	|  + 	| Shutdown / Reboot                	|  + 	| ADB access          	|  - 	|
| MMS in, out                   	|  ? 	| Wireless External monitor        	|  - 	| MTP access           	|  - 	|
| SMS in, out                    	|  + 	| Bluetooth                        	|  +- 	| WiFi			|  +	|
| Change audio routings          	|  +-	| Flight mode                      	|  + 	| Hotspot		|  +-	|
| Voice in calls                	|  + 	|

- **+** *Confirmed working.*
- **+-** *Working to some extent but with issues.*
- **-** *Not Working.*
- **?** *Not tested.*
- **--** *Global issue*

## Requirements
- Android 10 firmware for your device:
  - Redmi 9A dandelion: [LINK](https://xiaomifirmwareupdater.com/archive/miui/dandelion/).
  - Redmi 9C angelica: [LINK](https://xiaomifirmwareupdater.com/archive/miui/angelica/).

## Dandelion
- Download the latest rootfs:  [droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip](https://github.com/droidian-images/rootfs-api29gsi-all/releases).
- Download the adaptation package: [droidian-adaptation-garden.zip](https://bardia.tech/droidian/droidian-adaptation-garden.zip).
- Download [boot-dandelion.img](https://bardia.tech/droidian/boot-dandelion.img), [dtbo-dandelion.img](https://bardia.tech/droidian/dtbo-dandelion.img), [vbmeta-dandelion.img](https://bardia.tech/droidian/vbmeta-dandelion.img).
- Download our customized version of OrangeFox recovery [OrangeFox-R11-garden-droidian.img](https://bardia.tech/droidian/OrangeFox-R11-garden-droidian.img)

## Angelica
- Download the latest rootfs:  [droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip](https://github.com/droidian-images/rootfs-api29gsi-all/releases).
- Download the adaptation package: [droidian-adaptation-garden.zip](https://bardia.tech/droidian/droidian-adaptation-garden.zip).
- Download [boot-dandelion.img](https://bardia.tech/droidian/boot-angelica.img), [dtbo-dandelion.img](https://bardia.tech/droidian/dtbo-angelica.img), [vbmeta-dandelion.img](https://bardia.tech/droidian/vbmeta-angelica.img).

## Dandelion installation
- Flash boot-dandelion.img: `fastboot flash boot boot-dandelion.img`.
- Flash dtbo-dandelion.img: `fastboot flash dtbo dtbo-dandelion.img`.
- Flash vbmeta-dandelion.img: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta-dandelion.img`.
- Flash OrangeFox-R11-garden-droidian.img: `fastboot flash recovery OrangeFox-R11-garden-droidian.img`.
- Format userdata as ext4 from inside the recovery or via fastboot: `fastboot format:ext4 userdata`.
- Sideload droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip.
- Sideload droidian-adaptation-garden.zip
- Now boot into your device.
- *The first boot will take a while.*

## Angelica installation
- Flash boot-angelica.img: `fastboot flash boot boot-angelica.img`.
- Flash dtbo-angelica.img: `fastboot flash dtbo dtbo-angelica.img`.
- Flash vbmeta-dandelion.img: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta-angelica.img`.
- Flash OrangeFox-R11-garden-droidian.img: `fastboot flash recovery OrangeFox-R11-garden-droidian.img`.
- Format userdata as ext4 from inside the recovery or via fastboot: `fastboot format:ext4 userdata`.
- Sideload droidian-rootfs-api29gsi-arm64-xxxxxxxx.zip.
- Sideload droidian-adaptation-garden.zip
- Now boot into your device.
- *The first boot will take a while.*

## Notes
- The default password is `1234`.
- Xiaomi has not updated their kernel source tree and as a result some models of 9A and 9C have non functional display panels with our kernel.
- **Droidian GSIs are experimental! Bugs and missing features are expected.**

## Bugs
- Mobile data needs an APN to be set up from Settings -> Mobile -> Acess Point Names.
- RIL gets broken after switching airplane mode or modem off/on.
- Mobile data might stop working after making or recieving phone calls. Toggle Mobile Data from the settins off/on.
- Mobile data quick toggle doesn't work.
- Bluetooth can be used via the terminal using bluetoothctl command or using blueman **sudo apt install blueman** but does not work via the settings app.
- GPS works partially via Epiphany (tested with open street map)
- Signal strengh is reported at 1% but Mobile data and calls work just fine.
- Anything related to cameras do not work it is a global issue across all devices, it does however work in Waydroid which is currently not available on angelica and dandelion.
- Changing audio to speaker in calls does not work on dandelion but works on angelica.
- Earbuds work on both devices but earphones do not work on dandelion but work on angelica.
- Dual SIM functionality is currently not implemented in Phosh so only one SIM works at the moment.
- Just like bluetooth, hotspot does not work from settings either and has to be used from a GUI application (such as the default advanced network app) or from terminal.

## Final notes
- I'm not responsible for bricked devices, dead SD cards, thermonuclear war, or you getting fired because the alarm app failed.
- Please do some research if you have any concerns about features included in the products you find here before flashing it!
- YOU are choosing to make these modifications, and if you point the finger at me for messing up your device, I will laugh at you.

# Support
- Device specific telegram group: [@ut_angelica](https://t.me/ut_angelica).
- Droidian telegram group: [@DroidianLinux](https://t.me/DroidianLinux).

