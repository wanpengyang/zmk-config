# My Leeloo v1 by Clickety Split
This is my first custom split keyboard made by [Clickety Split](https://clicketysplit.ca). 

Keyboard Designer: [clicketysplit.ca]
GitHub: [ClicketySplit](https://github.com/ClicketySplit)
Hardware Supported: Pro Micro, Elite-C, and nice!nano v2


# Leeloo v1

## Features 
* 4x6x5m Split Keyboard
* Support for both Low Profile Choc switches, and Box/MX switches; 19.05mm x 19.05mm spacing.
* 90% of the switches are socketed; with the exception to the rotary encoder positions.
* Support for Alps Alpine EC11 Rotary Encoders—one on each side, in one of three locations.
* Support for OLED Displays or nice!view Displays.
  - nice!view displays require a wire to be soldered from the CS Pin on nice!view display to P0.22 or D4 on the nice!nano.
* Support for both 110mAh or 700mAh batteries.
* Solder pads for battery leads.
* Support for Alps Alpine Micro On/off switches.

# Building Leeloo's ZMK Firmware
ZMK Firmware: [Introduction to ZMK](https://zmk.dev/docs/)
Installation: [Installing ZMK](https://zmk.dev/docs/user-setup)
Customization: [Customizing ZMK](https://zmk.dev/docs/customization)
Development Environment: [Basic Setup](https://zmk.dev/docs/development/setup)

Add nice!view support in the build.yaml file:
```
include:
  - board: nice_nano_v2
    shield: leeloo_left nice_view_adapter nice_view
```


## Building Leeloo's ZMK Firmware with nice!view Displays
There are a couple of files that need to be adjusted before the build commands can be run.

### Edit the leeloo[_rev2].keymap File
Near the top 3rd of the leeloo[_rev2].keymap file, locate the following code block:

```
//nice_view_spi: &spi0 {
//	cs-gpios = <&pro_micro 4 GPIO_ACTIVE_HIGH>;
//};
```

Remove the forward slashes to resemble the following:
```
nice_view_spi: &spi0 {
	cs-gpios = <&pro_micro 4 GPIO_ACTIVE_HIGH>;
};
```

Save your changes and commit the file. GH action will automatically build the firmware.



# Support
If you have any questions with regards to Leeloo, please [Contact Clickety Split](https://clicketysplit.ca/pages/contact-us).

Clickety Split
For the love of split keyboards.
