#Spark Adafruit TSL2591 Light Sensor Driver #

This Spark driver is for the Adafruit TSL2591 Breakout, and is based on Adafruit's Unified Sensor Library (Adafruit_Sensor).

The driver supports manual or 'auto' gain. Adjusting the gain allows you to make the sensor more or less 'sensitive' to light (depending on if you are indoors or outdoors, for example):
```
tsl.setGain(TSL2561_GAIN_1X);      /* No gain ... use in bright light to avoid sensor saturation */
tsl.setGain(TSL2561_GAIN_16X);     /* 16x gain ... use in low light to boost sensitivity */
tsl.enableAutoGain(true);          /* Auto-gain ... switches automatically between 1x and 16x */
```

The driver also supports as automatic clipping detection, and will return '0' lux when the sensor is saturated and data is unreliable.

## About the TSL2591 ##

The TSL2561 is a 16-bit digital (I2C) light sensor, with adjustable gain and 'integration time'.  

Adjusting the 'integration time' essentially increases the resolution of the device, since the analog converter inside the chip has time to take more samples.  The integration time can be set as follows:
```
tsl.setIntegrationTime(TSL2561_INTEGRATIONTIME_13MS);      /* fast but low resolution */
tsl.setIntegrationTime(TSL2561_INTEGRATIONTIME_101MS);  /* medium resolution and speed   */
tsl.setIntegrationTime(TSL2561_INTEGRATIONTIME_402MS);  /* 16-bit data but slowest conversions */
```

More information on the TSL2591 can be found in the datasheet: http://www.adafruit.com/datasheets/TSL25911_Datasheet_EN_v1.pdf

