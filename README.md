# nrf52_remove_protection
Removing flash protection from the nRF52 using JLink + OpenOCD
1. openocd -c 'adapter driver jlink; transport select swd; source [find target/nrf52.cfg]'
2. telnet localhost 4444
3. nrf52.dap apreg 1 0x04 0x01
4. use command nrf52.dap apreg 1 0x0c to check protection is disable
SWD DPIDR 0x2ba01477
0x00000001 <----disable 
0x00000001 <----not disable 
5. disconnect jlink
6. Success

Reference link 
https://blog.dbrgn.ch/2020/5/16/nrf52-unprotect-flash-jlink-openocd/
