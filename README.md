# ha_tuya_watering
# Home Assistant automation and ZHA quirk for Tuya watering valve

This repository contains a Home Assistant automation and quirk for controlling Tuya watering valves. It allows you to automate the watering process based on various conditions and schedules.

My valve is a dual valve, zigbee only, Insoma-branded valve from Aliexpress, like this one.
https://www.aliexpress.com/item/1005007187642734.html

I am using ZHA to control the valve, and the automnation is triggered by time and weather conditions. More precisely, if the weather entity forecasts rain, the valve will not open.

## Pre-requisites

You need ZHA and the Meteorologisk institutt integration installed in Home Assistant.

## Installation

1. Copy the `ha_tuya_watering.py` file to your Home Assistant ZHA quirks directory, typically located at `/config/custom_zha_quirks/`.
2. Pair the Tuya watering valve with your Home Assistant instance using ZHA (this must be done after enabling the quirk, otherwise the valve will not be recognized).
3. If this is not working, check the valve device info in the ZHA integration. Mine shows up as TS0601
by TZE284_fhvpaltk. It was not supported by the quirk out of the box, so I had to modify it accordingly.
3. Copy the contents of `ha_tuya_watering.yaml` file to the file `automations.yaml`, or copy the file to `/config/automations/` if your automations are stored there.

## Customization

You can edit the automation to change the trigger time and the precipation threshold. The watering duration can be modified by selecting the device in ZHA and changing the irrigation time in `Configuration`.
As explained the in the last paragraph, it might be necessary to edit the quirk to match your device. The quirk is based on the Tuya watering valve quirk, so it should work with most Tuya watering valves.



