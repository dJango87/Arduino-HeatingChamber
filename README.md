# Arduino-HeatingChamber
A DIY temperature-controlled heating chamber

An Arduino UNO will serve as a microcontroller to read temperature and to control heating element.

The temperature sensor used in this project is a K-type thermocouple. Analog signal is amplified and converted to digital signal through a MAX31855K (cold-junction compensated thermocouple-to-digital converter). Data output is transferred in a signed 14-bit, SPI-compatible, and read-only format. Temperatures are resolved to 0.25 degC. Thermocouple accuracy of +-2 degC is achievable between temperatures of -200 degC and +700 degC.
More on MAX31855 is available here: https://www.adafruit.com/datasheets/MAX31855.pdf

PID algorithm is used to control the temperature. A fixed value (in this case the desired temperature) is determined. The algorithm will calculate a suitable output value according the the input values from the thermocouple and the fixed value.

In order to insert the fixed value, the first attempt is to use a potentiostat to vary voltage read by the analog input. The voltage value is then converted to temperature value. This attempt requires experimentation to test its practicality. Otherwise, an alternative has to be proposed.
