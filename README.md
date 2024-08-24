# Car-Antitheft-project
Goal: Design a digital system (Car Alarm) with sequential circuit (FSM) based on a set of specifications.

  ## Description of Anti-Theft System:
* Since your client is completely focused on her start-up, she wants an anti-theft system that's highly automated. The system is armed automatically after she turns off the ignition,  exits the car (i.e., the driver's door has opened and closed) and T_ARM_DELAY has passed. If there is a passenger and both the driver's door and passenger's doors are open, the    system arms itself after all the doors have been closed and T_ARM_DELAY has passed; that delay is restarted if a door is opened and reclosed before the alarm has been armed.

* Once the system has been armed, opening the driver's door the system begins a countdown. If the ignition is not turned on within the countdown interval (T_DRIVER_DELAY), the siren sounds. The siren remains on as long as the door is open and for some additional interval (T_ALARM_ON) after the door closes, at which time the system resets to the armed but silent state. If the ignition is turned on within the countdown interval, the system is disarmed.

* Always a paragon of politeness, your client opens the passenger door first if she's transporting a guest. When the passenger door is opened first, a separate, presumably longer, delay (T_PASSENGER_DELAY) is used for the countdown interval, giving her extra time to walk around to the driver's door and insert the key in the ignition to disarm the system.

* There is a status indicator LED on the dash. It blinks with a two-second period when the system is armed. It is constantly illuminated either the system is in the countdown waiting for the ignition to turn on or if the siren is on. The LED is off is the system is disarmed.

* So far this all is ordinary alarm functionality. But you're worried that a knowledgable thief might disable the siren and then just drive off with the car. So you've added an additional secret deterrent -- control of power to the fuel pump. When the ignition is off power to fuel pump is cut off. Power is only restored when first the ignition is turned on and then the driver presses both a hidden switch and the brake pedal simultaneously. Power is then latched on until the ignition is again turned off.

The diagram below lists all the sensors (inputs) and actuators (outputs) connected to the system:
<img width="744" alt="Screenshot 2024-08-24 at 11 05 56 PM" src="https://github.com/user-attachments/assets/f3a3072f-24f0-42b7-a034-03552ba76409">

## System Timings:

The system timings are based on four parameters (in seconds): the delay between exiting the car and the arming of the alarm (T_ARM_DELAY), the length of the countdown before the alarm sounds after opening the driver's door (T_DRIVER_DELAY) or passenger door (T_PASSENGER_DELAY), and the length of time the siren sounds (T_ALARM_ON). The default value for each parameter is listed in the table below, but each may be set to other values using the Time_Parameter_Selector, Time_Value, and Reprogram signals. Time_Parameter_Selector switches specify the parameter number of the parameter to be changed. Time_Value switches are a 4-bit value representing the value to be programmed -- a value in seconds between 0 and 15. Pushing the Reprogram button tells the system to set the currently selected parameter to Time_Value. Note that your system should behave correctly even if one or more of the parameters is set to 0.

<img width="761" alt="Screenshot 2024-08-24 at 11 07 58 PM" src="https://github.com/user-attachments/assets/931be4c8-415a-4763-b2a6-c4dc99c7d9a4">


