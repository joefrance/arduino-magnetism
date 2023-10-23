# arduino-magnetism
Control an electromagnet with an ESP32

# Parts list

ESP32:          https://www.amazon.com/dp/B08D5ZD528?ref=ppx_yo2ov_dt_b_product_details&th=1
Electormagnet:  https://www.amazon.com/dp/B07H3V8N2Q?psc=1&ref=ppx_yo2ov_dt_b_product_details
Jumper wires:   https://www.amazon.com/gp/product/B01EV70C78/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1 

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