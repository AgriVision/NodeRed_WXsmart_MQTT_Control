NodeRed_WXsmart_MQTT_Control
============================

Node Red Dashboard to control WXsmart soldering station with MQTT

### About

This is a Node Red dashboard to control the Weller WXsmart soldering station.
This code belongs to my 
[Element14 Weller WXsmart review](https://community.element14.com/products/roadtest/rv/roadtest_reviews/1691/weller_wxsmart_review).

The flow listens for WXsmart messages, defined by WXSMART_TOPIC in the environment file in the Node-Red root folder (for serialnumber fill in your stations serial number):

```
pi@myrpi:~ $ cat .node-red/environment 

WXSMART_TOPIC=WXSMART/serialnumber/STATUS/#

pi@myrpi:~ $ 
```

It filters for specific strings, such as Tool 1 temperature and power, and displays them in a widget on the dashboard. It also checks if it's receiving ONLINE from the station, if not it's probably off, and with a watchdog timer, the dashboard will indicate OFFLINE.
The code is far from finished, but it provides enough tools to build on.
