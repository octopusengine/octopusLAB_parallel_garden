# Micropython on OctopusLAB IoTboard (with ESP32)

## pinouts
<pre>
pinouts/olab_esp32_iot_board1.py

BUILT_IN_LED = 2

> I2C:
I2C_SCL_PIN = 22
I2C_SDA_PIN = 21
Determine what we have connected to I2C:
isOLED =  0x3c in i2cdevs
bhLight = 0x23 in i2cdevs
bh2Light= 0x5c in i2cdevs
tslLight= 0x39 in i2cdevs

---esp32---IoT board:
PIEZZO_PIN =  27
WS_LED_PIN =  15
ANALOG_PIN =  36
ONE_WIRE_PIN= 32 # DEV1_PIN  > Dallas temperature
RELAY_PIN =   33
MFET_PIN =    14

BUTT1_PIN =   25 # up
BUTT2_PIN =   12 # o  #TDI
BUTT3_PIN =   13 # dw #TCK

PWM1_PIN = 17    # PWM/servo > pwr for moisture
PWM2_PIN = 16
PWM3_PIN = 4

DEV1_PIN = 32
DEV2_PIN = 26

> inputs:
I39_PIN = 39
I34_PIN = 34
I35_PIN = 35     # analog in for moisture
</pre>

--

## config
<pre>
config/garden.json
{
    "version": 1,       // version of json config file
    "debug": 1,
    "uid": "3ac5167c",  // hw device ID
    "place": "orasol",  // place or group of devices
    "timeinterval": 10, // [minutes] -> every 10 min - default
    "rundemo": 0,       // automatic start-up test 
    "tempoffset": -1,
    
    "mtemp": 1,         // set sensors/devices: on/off [1/0]
    "mlight": 1,
    "mmoist": 1,
    "manalog": 0,
    "manlight": 0,
    "mantemp": 0,
    "mlight2": 0,
    
    "startlight": 9,    // light on, time: [hour] 
    "stoplight": 18,    // light off, time: [hour]
    "lightintensity": 500,
    "pumpnodes": [ 7, 15, 22 ],
    "pumpduration": 3,  // [minutes]
    
    "uid8": 1,
    "cloudconfig": 1,   // once load
    "cloudconfdynam": 1,// load every timeinterval
    "cloudupdate": 1    // update FW - prepare
}
</pre>

> https://github.com/octopusengine/octopuslab/tree/master/esp32-micropython
