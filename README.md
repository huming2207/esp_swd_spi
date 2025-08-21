# SWD over ESP32 SPI

## Known issue

### SPI timing

So far SPI timing has to be 40MHz when CPU clock speed is 240MHz (APB clock 160MHz?), or 20MHz when CPU clock speed is 160MHz (APB clock 80MHz?). 

If `SPI.clock.clkdiv_pre` is set to anything non-zero, the target will not send ACK or ACK with FAULT result. Same for `clkcnt_n`, `clkcnt_h` and `clkcnt_l`.

### Pin mapping

Currently the pins are hard-coded to GPIO12 for SWCLK and GPIO11 for SWDIO. I need to try and see if they works on any other pins or not.

### Fallback to GPIO bitbang is removed

Need some cleanup before putting this back
