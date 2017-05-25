A small minicom-like tool

Compile:

	sudo apt install libreadline-dev

	cmake . && make -j4

Usage:

	run: sudo ./microcom -s 115200 -p /dev/ttyUSB0

	exit: Ctrl+\ && quit
