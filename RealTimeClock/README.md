# RealTimeClock

This is a modification to the `runtime.sh` of Onion UI 4.3.0 which makes the system time sync with the built-in RTC upon system boot.

RTC was seemingly added to the board around early 2024, which allows using the `hwclock` command to sync the system time. Specifically I've changed the `update_time()` function (line 749), removing all of the old code and replacing it with a simple `hwclock --hctosys` command.

## Disclaimer

This change has only been tested on my personal device, where it has been deemed functional during quick testing. If you choose to use this modified script, take a backup of your SD card before doing so.

Before using this script, make sure you have a newer revision of the MMP that comes with the RTC. The effect of this change is untested on devices with no RTC.

## Installation

Overwrite the `runtime.sh` file in your SD card's `.tmp_update` folder with the modified version.
