### Tools
1. RasberryPi 
2. Test Clip for SPI

### Target Board for Lab Exercise
1. TL-WR886N - For UART and SPI data extraction
2. TL-WR1043ND - For UART and JTAG


### Lab Exercise for SPI Flash Data Extraction
Step 1: Attach the test clip according to the RasberryPi SPI configuration.
Using GPIO 19, 21, 23 and 24 only

<img src="TL-WR886N/Pics/pi%20spi%20pinouts.png" height="400" width="400"> 

Step 2: Use the test clip and connect it to the TL-WR886N SPI chip

<img src="TL-WR886N/Pics/spi%20connection%20to%20target.jpg" height="400" width="400"> 

>[!INFO]
>This is a SPI Flash GD25Q16C (2MB) and their pinouts
> Connect WP and HOLD pins to VCC

<img src="TL-WR886N/Pics/spi%20flash.jpg" height="400" width="400"> 

<img src="TL-WR886N/Pics/GD25Q16C%20pinouts.png" height="400" width="400"> 

Step 3: Using flashrom to extract from SPI
>$sudo flashrom -p linux_spi:dev=/dev/spidev0.0,spispeed=8000 -r spi_flash.bin

<img src="TL-WR886N/Pics/flashrom%20command%20screenshot.png" height="400" width="600"> 

### Lab Exercise to Access UART
UART pinouts of TL-WR886N

<img src="TL-WR886N/Pics/TL-WR886N%20UART%20Pinout.jpg" height="400" width="400"> 

UART pinouts of TL-WR1043ND

<img src="TL-WR1043ND/TL_WR1043ND%20UART.jpg" height="400" width="400"> 

Step 1: Rasberry Pi UART configuration, follow the pinout and connect to the transmit and receive pins of the UART idenitfied on the target

<img src="TL-WR1043ND/pi_uart_pinout.png" height="400" width="500"> 

Step 2: Use minicom tool to interact with the OS

>$ minicom -s /dev/ttyS0 <br>
115200 8N1 <br>
Pi Pinout: Pin 8 (Tx)  Pin 10 (Rx)

UART Shell

<img src="TL-WR886N/Pics/uart_shell.png" height="400" width="400"> 

Command to display the flash Layout

<img src="TL-WR886N/Pics/flash_layout.png" height="450" width="400"> 
