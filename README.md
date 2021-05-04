# nrf52_remove_protection
Removing flash protection from the nRF52 using JLink + OpenOCD
1.openocd -c 'interface jlink; transport select swd; source [find target/nrf52.cfg]'
2.telnet localhost 4444
3.nrf52.dap apreg 1 0x04 0x01
4.disconnect jlink
5.Success

Reference link 
https://blog.dbrgn.ch/2020/5/16/nrf52-unprotect-flash-jlink-openocd/
