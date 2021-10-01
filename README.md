# audiBEM

### Summary


  This "project" aims to use genuine AUDI A6 4FH J644 Battery Energy Monitor(BEM)... ![BEM Picture](pictures/partnumber.jpg) ...as realtime current measuring probe 
with data logging feature and/or online transmission to remote computer.

### Motivation

  Since automotive engineers decided to stop using terminal #15 (baterry+ through ignition switch) for sleep and wake up
of car electronic units (Steuergerate :smile:), sometimes bad things happen. Instead of using terminal #15 nowadays [CAN-BUS](https://en.wikipedia.org/wiki/CAN_bus) is more
likely used for this purpose. Lot of headache can occur, when investigating cars with this "new feature" for parasitic current drain.
When car is stopped and locked, it takes some time until devices enters sleep mode. Every device is hibernated probably after certain datagram 
is sent over CAN-BUS. Sometimes, when things are going wrong, you can find your car in the middle of nowhere after two-three hours with weak battery and you are
unable to start the engine. Such current drain is intermittent and it is very hard to find. Therefore it would be helpful to constantly read car energy consumption
and get notified of unusual conditions.


### Device teardown

  There is obviously some kind of Hall element detection type used: ![BEM Inside](pictures/pcb2.jpg) Principle of operation can look like this:  ![](https://hiokiusa.com/wp-content/uploads/2019/05/Current-Probes5-300x188.png)  



Some parts identification: 

* TMS470 980 - seems to be ARM based automotive MCU
* Bosch 30589 0625 - unknown - probably some kind of another MCU
* 12MHz oscillator - upper right corner, probably for TMS470
* 16kbit serial SPI bus EEPROM - upper left corner (95160W3)
* TJA1054T - CAN-BUS transceiver


