# UHD 4.9.0.0 with ANTSDR support

This tree starts from the stock UHD 4.9.0.0 release with host-side changes ported from the Microphase ANTSDR UHD fork (circa UHD 4.1), plus minor GPS compatibility fixes. Key additions:

- New ANT device implementation under host/lib/usrp/ant (device discovery, control, streaming).
- Transport helpers and radio control core (radio_ctrl_core_3000) copied from the ANT fork.
- Build wiring to enable ANT via ENABLE_ANT and include AD936x driver for ANT.
- GPSDO handling updated to support Microphase GN->GP NMEA normalization (gps_ctrl::make(..., is_mp)).

Firmware: Matching ANTSDR FPGA/firmware sources live in antsdr_uhd/firmware (built with Vivado 2019.1). Flashing the ANT bitstream/BOOT.bin from that tree is recommended before testing.

Testing: After building host, run uhd_find_devices/uhd_usrp_probe to verify ANTSDR detection; set clock/pps sources as needed.
