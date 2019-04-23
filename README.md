# M5Stack Firmware

## Description
You can share your firmware and other M5 fans can use it by M5Burner.But if you want to share your firmware here, you should follow some rules below.

## Demo
* [UIFlow Firmware](https://github.com/EeeeBin/UIFlow-Firmware) (Multi Version Demo)
* [Test Firmware](https://github.com/curdeveryday/test-firmware) (Single Version Demo)

## Quickstart
### __1.Folder Structure__
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

### __2.File *m5burner.json* Format__
Some infomation must in your *m5burner.json*.For example:
``` javascript
{
    // Firmware name
    "name": "UIFlow",

    // Description
    "description": "maybe nooooooooo bug",

    // Keywords
    "keywords": "ESP32, Micropython",

    // Author
    "author": "EeeeBin",

    // The github repository of the firmware (Required)
    "repository": "https://github.com/EeeeBin/UIFlow-Firmware",

    // If there are multiple categories of firmware, this field will be a array.
    // Otherwise, it will be a key-value structure.
    // (Single version demo: https://github.com/curdeveryday/test-firmware)
    "firmware_category": [
        // Category infomation
        {
            // Category name
            "Stack-EN": {
                // Firmware path
                "path": "firmware_en",

                // Applicable Devices
                "device": ["M5Stack Core"],

                // Default baudrate
                "default_baud": 921600
            }
        },
        
        // Same of above ...
        {
            "Stack-CN": {
                "path": "firmware_cn",
                "device": [
                    "M5Stack Core"
                ],
                "default_baud": 921600
            }
        },
        {
            "Stick": {
                "path": "firmware_Stick",
                "device": [
                    "M5Stack Stick"
                ],
                "default_baud": 921600
            }
        },
        {
            "StickC": {
                "path": "firmware_StickC",
                "device": [
                    "M5Stack StickC"
                ],
                "default_baud": 750000
            }
        }
    ],

    // Firmware version
    "version": "1.2.3",

    // Firmware platform
    "framework": "Micropython"
}
```

### __3.Folder *firmware*__
The name of files in *firmware* must follow the rules.

#### __Please follow the rule `filename` = `name` + "_" + `flash address`.__

For example, if you have a file _**a.bin**_ and it flash address is _**0x1000**_.It should be named _**a_0x1000.bin**_

### __4.Pull Request__
After meeting the above rules, you should fork our [repository](https://github.com/m5stack/M5Stack-Firmware) and add your firmware repository in `firmware-repo.list`.Now, you submit a pull request in [M5Stack Firmware](https://github.com/EeeeBin/UIFlow-Firmware/pulls).We will review your firmware and add it in M5Burner.This operation is only required when the firmware is first submitted. If the firmware is updated, M5Burner will automatically obtain the new firmware address.

## Download M5Burner
- [Windows](http://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/software/M5Burner.zip)

## Contribution
Last but certainly not least, a big *__Thank You__*! To the following folks that helped to make M5Stack even better.
- [EeeeBin](https://github.com/EeeeBin): Add firmware UIFlow [PR #1](https://github.com/m5stack/M5Stack-Firmware/pull/1)