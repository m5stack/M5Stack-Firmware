# M5Stack Firmware
You can share your firmware and other M5 fans can use it by M5Burner.But if you want to share your firmware here, you should follow some rules below.

## Demo
* [UIFlow Firmware](https://github.com/sakabin/UIFlow-Firmware)

## Quickstart
### __Folder Structure__
Here some requirements to your firmware directory.For example:
```
│  README.md
│  m5burner.json (Required)
│
└─ firmware (Required)
        bootloader_0x1000.bin
        MicroPython_0x10000.bin
        partitions_mpy_0x8000.bin
        phy_init_data_0xf000.bin
        spiffs_image_0x170000.img
        ......
```
> Your firmware root directory must have file *m5burner.json* and folder *firmware*.
---
### __File *m5burner.json* Format__
Some infomation must in your *m5burner.json*.For example:
``` json
{
    // Your firmware name.
    "name": "",
    // Your firmware version.
    "version": "",
    // Your firmware github repo url.
    "repository": "",
    "author": "",
    "description": "",
    "keywords": "",
    "firmware-path": "",
    "framework": ""
}
```
> Here the *name*, *version* and *repository* are required.
---
### __Folder *firmware*__
The name of files in *firmware* must follow the rules.

#### __Please follow the rule `filename` = `name` + "_" + `flash address`.__

For example, if you have a file _**a.bin**_ and it flash address is _**0x1000**_.It should be named _**a_0x1000.bin**_
