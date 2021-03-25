# PTA Controller Application

The PTA Controller application is custom application built on the Flex stack, designed to help customers evaluate coexistence features on the silicon labs devices.
The Zigbee radios act as peripheral radio devices, and require a controller device to react and respond to coexistence requests.
The PTA Controller application implements this and allows users control to the behavior of the PTA Controller to evaluate the corresponding behavior of the peripheral radio device.

## Commands in the PTA Controller Application

* __Sample Command:__ Command description
	* __Command Argument:__ Argument description



### List of Commands Available in the PTA Controller Application

* __help:__ Print out list and description of commands available

* __configuration:__ Print out the current configuration of features

* __request:__ Set REQUEST signal polarity
	* __activehigh:__ sets the signal polarity active HIGH
	* __activelow:__ sets the signal polarity active LOW

* __grant:__ Set GRANT signal polarity
	* __activehigh:__ sets the signal polarity active HIGH
	* __activelow:__ sets the signal polarity active LOW

* __priority:__ Set PRIORITY signal polarity
	* __activehigh:__ sets the signal polarity active HIGH
	* __activelow:__ sets the signal polarity active LOW

* __rho:__ Set RHO signal polarity
	* __activehigh:__ sets the signal polarity active HIGH
	* __activelow:__ sets the signal polarity active LOW


* __grantabort:__ Enable/Disable GRANT Abort feature, and set abort percentage
	* __0:__ disables GRANT Abort
	* __1-100:__ enables GRANT Abort and sets percentage of GRANTS that are aborted


* __grantdelay:__ Enable/Disable GRANT Delay feature, and set delay percentage
	* __0:__ disables GRANT Delay
	* __1-100:__ enables GRANT Delay and sets percentage of GRANTS that are delayed


* __grantdeny:__ Enable/Disable GRANT Deny feature, and set deny percentage
	* __0:__ disables GRANT Deny
	* __1-100:__ enables GRANT Deny and sets percentage of GRANTS that are denied


* __rhofeature:__ Enable/Disable Radio Hold Off (RHO) feature, and set rho percentage
	* __0:__ disables RHO feature, and sets pin to High Z mode.
	* __1-100:__ enables RHO and sets percentage of Radio Hold Off requests


* __txStreamToggling:__ Output a toggling stream for a specified time, up to 60 seconds. Note: This feature sets GRANT to always asserted
	* __1-60:__ time for which to output stream

* __setTxStream:__ Output a stream
	* __1:__ Enable stream
	* __0:__ Disable stream

* __setPower:__ Set the current transmit power in deci dBm, or raw units if 'raw' is specified
	* __[power]:__ Output power to set (range depends on capabilities of radio device. Refer to datasheet of device for more info)
	
* __getPower:__ Get the current transmit power in deci dBm
	
* __setchannel:__ Set the current radio channel
	* __0-15:__ Value 0 corresponds to Zigbee channel 11

* __getchannel:__ Get the current radio channel




## Using the PTA Controller Application
The PTA Controller application is ready to use after compilation with the following default features:

* REQUEST is set to Active HIGH
* GRANT is set to Active HIGH
* PRIORITY is set to Active HIGH
* RHO is set to Active HIGH, but the feature is disabled and the pin is set to High Z mode
* GRANT Abort, GRANT Delay, and GRANT Deny are disabled
* No stream is active

To change any of the default configurations, use the commands previously listed.
Use the __*configuration*__ command to print out current configuration.

The PTA Controller application can also hinder network traffic to test behavior of the peripheral radio device in such conditions.
The __*txStreamToggling*__ command outputs a periodic stream for a specified time, causing packets or sections of packets on the network to get corrupted.
