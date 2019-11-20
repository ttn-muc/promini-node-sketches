# ProMini LoRaWAN node sample sketches

Some sketches for the ProMini LoRaWAN node, described here: https://www.thethingsnetwork.org/labs/story/creating-a-ttn-node

## Notes on replacing the ProMini
There's an alternative to the "normal" Arduino Pro Mini, the [Pro Mini XL](https://hackaday.io/project/165122-searching-for-a-better-pro-mini), which uses an ATmega1284p instead of the ATmega328p. It's compatible to the ProMini Node PCB, but you need to adjust the pin mapping for the LMIC library, like so:

```
const lmic_pinmap lmic_pins = {
  .nss = 4,
  .rxtx = LMIC_UNUSED_PIN,
  .rst = LMIC_UNUSED_PIN,
  .dio = {12, 13, LMIC_UNUSED_PIN}
};
```
