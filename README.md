# nrf52_remove_protection
# Removing flash protection from the nRF52 using JLink + OpenOCD
## 1. Create service
```openocd -c 'adapter driver jlink; transport select swd; source [find target/nrf52.cfg]'``` 
## or 
```openocd -c 'interface jlink; transport select swd; source [find target/nrf52.cfg]'``` 
## 2. Connect 
```telnet localhost 4444```
## 3. Remove flash protection 
```nrf52.dap apreg 1 0x04 0x01```
## 4. Check protection status
```nrf52.dap apreg 1 0x0c```\
SWD DPIDR 0x2ba01477\
0x00000001 <----flash protection has been removed.\
0x00000000 <----flash protection not removed.\
## 5. finish and disconnect jlink\
Reference link 
https://blog.dbrgn.ch/2020/5/16/nrf52-unprotect-flash-jlink-openocd/
