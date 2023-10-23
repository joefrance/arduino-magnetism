# arduino-magnetism
Control an electromagnet with an ESP32

# Warning ! ! !

- I do not take any responsibilty for damage to your eletronics or otherwise. Use this at your own risk.
- The electromagnet may heat up significantly if left in the HIGH/on state for long periods of time.
- For best results DO NOT CONNECT THE ELECTORMAGNET TO THE ESP32 TILL YOU UNPLUG IT FROM YOUR USB ON YOUR LAPTOP.
- Program the ESP32 with your code. Then unplug it from your laptop.
- Then reconnect to wall-power via a USB power adapter. This configuration will run the ESP32 and activate/deactivate the magnet.
- You may view the change in magnetism with the visualization sheet below and the LED on the ESP32.

# Parts list

ESP32:          https://www.amazon.com/dp/B08D5ZD528?ref=ppx_yo2ov_dt_b_product_details&th=1

Electormagnet:  https://www.amazon.com/dp/B07H3V8N2Q?psc=1&ref=ppx_yo2ov_dt_b_product_details

Jumper wires:   https://www.amazon.com/gp/product/B01EV70C78/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1 

See mag field:  https://www.amazon.com/gp/product/B0C66CYSC7/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1

# Wiring diagram

```
Magnet.GND <===> ESP32.GND
Magnet.VCC <===> ESP32.VIN
Magnet.SIG <===> ESP32.D2
```

# Code

```
void setup() {
  // put your setup code here, to run once:
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(LED_BUILTIN, HIGH);
  int minutesMinHIGH = 1 * 60 * 1000;
  int minutesMaxHIGH = 30 * 60 * 1000;
  int randomMinutesHIGH = random(minutesMinHIGH, minutesMaxHIGH);
  delay(randomMinutesHIGH);
  
  digitalWrite(LED_BUILTIN, LOW);
  int minutesMinLOW = 1 * 60 * 1000;
  int minutesMaxLOW = 30 * 60 * 1000;
  int randomMinutesLOW = random(minutesMinLOW, minutesMaxLOW);
  delay(randomMinutesLOW);

}
```