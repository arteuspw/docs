---
description: Guide to flashing your Cartographer probe with new or updated firmware.
---
# Firmware Update
## Which Firmware Should I use?&#x20;
Selecting the correcet firwmare is essential for the operation of the probe, please check which probe you have, and which mode it is being used in and cross reference the table below.&#x20;
### Cartographer v1 RP2040
<table>
   <thead>
      <tr>
         <th width="123">Mode</th>
         <th width="176">Firmware</th>
         <th width="89">Link</th>
         <th>Notes</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>USB</td>
         <td>carto-rp2040.uf2</td>
         <td><a href="https://github.com/Cartographer3D/cartographer-klipper/tree/master/firmware/v1%20-%20rp2040">GitHub</a></td>
         <td>Only USB Compatible - No Katapult Bootloader Required</td>
      </tr>
   </tbody>
</table>

### Cartographer v2 w/ Input Shaper (USB or CAN)
With Cartographer v2, the device will only work in the mode that it was purchased. This is a hardware limitation. The CAN Probe can be forced to work in USB Mode, but is unreliable and requires hardware modifications, this is not something we recommend right now.&#x20;
#### USB Version

<table>
   <thead>
      <tr>
         <th width="228">Firmware</th>
         <th width="127">Type</th>
         <th width="140">Address</th>
         <th>Notes</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <h4><a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v2/Katapult_USB.bin">Katapult_USB.bin</a></h4>
         </td>
         <td>Bootloader (Katapult)</td>
         <td>0x08000000</td>
         <td></td>
      </tr>
      <tr>
         <td>
            <h4><a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v2/Cartographer_USB_8kib_offset.bin">Cartographer_USB.bin</a></h4>
         </td>
         <td>Firmware (Klipper)</td>
         <td>0x08002000</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
   </tbody>
</table>

#### CAN Version

<table>
   <thead>
      <tr>
         <th width="229">Firmware</th>
         <th>Type</th>
         <th>Address</th>
         <th width="95" align="center">Baudrate</th>
         <th>Notes</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Katapult_CAN_100000.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v2/Katapult_CAN_1000000.bin">Link</a>)</td>
         <td>Bootloader (Katapult)</td>
         <td>0x08000000</td>
         <td align="center">1M</td>
         <td></td>
      </tr>
      <tr>
         <td>Cartographer_CAN_1000000_8kib_offset.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v2/Cartographer_CAN_1000000_8kib_offset.bin">Link</a>)</td>
         <td>Firmware (Klipper)</td>
         <td>0x08002000</td>
         <td align="center">1M</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
      <tr>
         <td>Cartographer_CAN_250000_8kib_offset.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v2/Cartographer_CAN_500000_8kib_offset.bin">Link</a>)</td>
         <td>Firmware (Klipper)</td>
         <td>0x08002000</td>
         <td align="center">250K</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
      <tr>
         <td>Cartographer_CAN_500000_8kib_offset.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v2/Cartographer_CAN_500000_8kib_offset.bin">Link</a>)</td>
         <td>Firmware (Klipper)</td>
         <td>0x08002000</td>
         <td align="center">500K</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
   </tbody>
</table>

### Cartographer v3 w/ Input Shaper (USB/CAN)

Cartographer v3 by default will come pre-flashed for CAN. You can switch between both USB and CAN modes via firmware with no hardware modification required.&#x20;

#### USB / CAN Version

<table>
   <thead>
      <tr>
         <th>Firmware</th>
         <th width="125">Type</th>
         <th width="137">Address</th>
         <th width="105">Baudrate</th>
         <th>Note</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Full_Cartographer_USB_v3.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v3/Full_Cartographer_USB_v3.bin">Link</a>)</td>
         <td>Bootloader &#x26; Firmware Combined</td>
         <td>0x08000000</td>
         <td>n/a</td>
         <td>This is the only firmware you need, you don't need to flash the bootloader or firmware seperately. </td>
      </tr>
      <tr>
         <td>Full_Cartographer_CAN_1M_v3.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v3/Full_Cartographer_CAN_1M_v3.bin">Link</a>)</td>
         <td>Bootloader &#x26; Firmware Combined</td>
         <td>0x08000000</td>
         <td>1M</td>
         <td>This is the only firmware you need, you don't need to flash the bootloader or firmware seperately. </td>
      </tr>
      <tr>
         <td>Katapult_250k_withSwitch.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v3/Katapult_250k_withSwitch.bin">Link</a>)</td>
         <td>Bootloader (Katapult)</td>
         <td>0x08000000</td>
         <td>250K</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
      <tr>
         <td>Katapult_500k_withSwitch.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v3/Katapult_500k_withSwitch.bin">Link</a>)</td>
         <td>Bootloader (Katapult)</td>
         <td>0x08000000</td>
         <td>500K</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
      <tr>
         <td>Cartographer_CAN_250000_8kib_offset.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v3/Cartographer_CAN_250000_8kib_offset.bin">Link</a>)</td>
         <td>Firmware (Klipper)</td>
         <td>0x08002000</td>
         <td>250K</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
      <tr>
         <td>Cartographer_CAN_500000_8kib_offset.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v3/Cartographer_CAN_500000_8kib_offset.bin">Link</a>)</td>
         <td>Firmware (Klipper)</td>
         <td>0x08002000</td>
         <td>500K</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
      <tr>
         <td>Cartographer_CAN_1000000_8kib_offset.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v3/Cartographer_CAN_1000000_8kib_offset.bin">Link</a>)</td>
         <td>Firmware (Klipper)</td>
         <td>0x08002000</td>
         <td>1M</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
      <tr>
         <td>Cartographer_USB_v3_8kib_offset.bin (<a href="https://github.com/Cartographer3D/cartographer-klipper/blob/master/firmware/v3/Cartographer_USB_v3_8kib_offset.bin">Link</a>)</td>
         <td>Firmware (Klipper)</td>
         <td>0x08002000</td>
         <td>n/a</td>
         <td>8KiB Offset required, so needs ot 0x08002000</td>
      </tr>
   </tbody>
</table>
