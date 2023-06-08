# SHELL := /bin/bash

BOARD_NAME=lpcxpresso55s69_cpu0
PROJECT_DIR=~/micropython/ports/zephyr
TTY_PORT=/dev/tty.usbmodem0007257803501
BAUD_RATE=115200
ZEPHYR_SOURCE=~/zephyrproject/zephyr/zephyr-env.sh 

default: clean build flash

config:
	source $(ZEPHYR_SOURCE) && west build -t menuconfig

build:
	source $(ZEPHYR_SOURCE) && west build -p always -b $(BOARD_NAME) $(PROJECT_DIR)

flash: 
	source $(ZEPHYR_SOURCE) && west flash

clean:
	rm -rf ./build

screen:
	screen $(TTY_PORT) $(BAUD_RATE)