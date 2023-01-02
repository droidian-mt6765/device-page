## Features & Usability

|                               	|    	|                                  	|    	|                      	|   	|
|-------------------------------	|----	|----------------------------------	|----	|----------------------	|---	|
| Manual brightnes              	|  ✅ 	| Battery lifetime > 24h from 100% 	|  ✅ 	| Automatic brightness  |  ✖️ 	|
| No reboot needed for 1 week      	|  ✅	| Fingerprint reader  	                |  ✖️ 	| Waydroid		|  ✅	|
| Torchlight                    	|  ✅✅	| Boot into UI                     	|  ✅ 	| GPS                 	|  ✖️ 	|
| Vibration                     	|  ✅ 	| Hardware video playback          	|  ✅ 	| Proximity          	|  ✖️ 	|
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
- Download the latest rootfs:  [droidian-OFFICIAL-phosh-phone-rootfs-api29-armhf-nightly_XXXXXXXX.zip](https://github.com/droidian-images/droidian/releases/tag/nightly).
- Download the adaptation package: [adaptation-droidian-garden.zip](https://github.com/droidian-mt6765/adaptation-droidian-garden/releases/download/adaptation/adaptation-droidian-garden.zip).
- Download [boot-dandelion.img](https://github.com/droidian-mt6765/kernel-xiaomi-mt6765/releases/download/dandelion/boot-dandelion.img), [dtbo-dandelion.img](https://github.com/droidian-mt6765/kernel-xiaomi-mt6765/releases/download/dandelion/dtbo-dandelion.img), [vbmeta-dandelion.img](https://github.com/droidian-mt6765/kernel-xiaomi-mt6765/releases/download/dandelion/vbmeta-dandelion.img).
- Download our customized version of OrangeFox recovery [OrangeFox-R11-garden-droidian.img](https://garden.bardia.tech/OrangeFox-R11-garden-droidian.img)

## Angelica
- Download the latest rootfs:  [droidian-OFFICIAL-phosh-phone-rootfs-api29-armhf-nightly_XXXXXXXX.zip](https://github.com/droidian-images/droidian/releases/tag/nightly).
- Download the adaptation package: [adaptation-droidian-garden.zip](https://github.com/droidian-mt6765/adaptation-droidian-garden/releases/download/adaptation/adaptation-droidian-garden.zip).
- Download [boot-angelica.img](https://github.com/droidian-mt6765/kernel-xiaomi-mt6765/releases/download/angelica/boot-angelica.img), [dtbo-angelica.img](https://github.com/droidian-mt6765/kernel-xiaomi-mt6765/releases/download/angelica/dtbo-angelica.img), [vbmeta-angelica.img](https://github.com/droidian-mt6765/kernel-xiaomi-mt6765/releases/download/angelica/vbmeta-angelica.img).
- Download our customized version of OrangeFox recovery [OrangeFox-R11-garden-droidian.img](https://garden.bardia.tech/OrangeFox-R11-garden-droidian.img)

## Dandelion installation
- Flash boot-dandelion.img: `fastboot flash boot boot-dandelion.img`.
- Flash dtbo-dandelion.img: `fastboot flash dtbo dtbo-dandelion.img`.
- Flash vbmeta-dandelion.img: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta-dandelion.img`.
- Flash OrangeFox-R11-garden-droidian.img: `fastboot flash recovery OrangeFox-R11-garden-droidian.img`.
- Format userdata as ext4 from inside the recovery or via fastboot: `fastboot format:ext4 userdata`.
- Now boot into recovery.
- Go into sideload mode and sideload droidian-OFFICIAL-phosh-phone-rootfs-api29-armhf-nightly_XXXXXXXX.zip: `adb sideload droidian-OFFICIAL-phosh-phone-rootfs-api29-armhf-nightly_XXXXXXXX.zip`
- Go into sideload mode and sideload adaptation-droidian-garden.zip: `adb sideload adaptation-droidian-garden.zip`
- Now boot into your device.
- If for some reason sideload or recovery did not work out for you should try my second installation method:
- Download the adaptation script (not the adaptation package): [adaptation-garden-script.zip] (https://github.com/droidian-mt6765/adaptation-garden-script/releases/download/adaptation/adaptation-garden-script.zip).
- Download PBRP: [PBRP-3.1.0.img] (https://garden.bardia.tech/PBRP-3.1.0.img)
- Flash PBRP-3.1.0.img: `fastboot flash recovery PBRP-3.1.0.img`.
- Now boot into recovery
- Now extract adaptation-garden-script.zip on your PC/Laptop and push it to your device: adb push adaptation-garden-script /tmp
- Change directory to /tmp and run the script: cd /tmp/adaptation-garden-script && chmod +x install.sh && ./install.sh
- Now boot into your device.
- *The first boot will take a while.*

## Angelica installation
- Flash boot-angelica.img: `fastboot flash boot boot-angelica.img`.
- Flash dtbo-angelica.img: `fastboot flash dtbo dtbo-angelica.img`.
- Flash vbmeta-dandelion.img: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta-angelica.img`.
- Flash OrangeFox-R11-garden-droidian.img: `fastboot flash recovery OrangeFox-R11-garden-droidian.img`.
- Format userdata as ext4 from inside the recovery or via fastboot: `fastboot format:ext4 userdata`.
- Now boot into recovery.
- Go into sideload mode and sideload droidian-OFFICIAL-phosh-phone-rootfs-api29-armhf-nightly_XXXXXXXX.zip: `adb sideload droidian-OFFICIAL-phosh-phone-rootfs-api29-armhf-nightly_XXXXXXXX.zip`
- Go into sideload mode and sideload adaptation-droidian-garden.zip: `adb sideload adaptation-droidian-garden.zip`
- Now boot into your device.
- If for some reason sideload or recovery did not work out for you should try my second installation method: 
- Download the adaptation script (not the adaptation package): [adaptation-garden-script.zip] (https://github.com/droidian-mt6765/adaptation-garden-script/releases/download/adaptation/adaptation-garden-script.zip).
- Download PBRP: [PBRP-3.1.0.img] (https://garden.bardia.tech/PBRP-3.1.0.img)
- Flash PBRP-3.1.0.img: `fastboot flash recovery PBRP-3.1.0.img`.
- Now boot into recovery 
- Now extract adaptation-garden-script.zip on your PC/Laptop and push it to your device: adb push adaptation-garden-script /tmp
- Change directory to /tmp and run the script: cd /tmp/adaptation-garden-script && chmod +x install.sh && ./install.sh
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
- GPS doesn't work.
- Signal strengh is reported at 1% but Mobile data and calls work just fine.
- Anything related to cameras only works in Waydroid which.
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
