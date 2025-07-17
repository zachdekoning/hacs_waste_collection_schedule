# Stadtwerke Hürth

Stadtwerke Hürth is supported by the generic [ICS](/doc/source/ics.md) source. For all available configuration options, please refer to the source description.


## How to get the configuration arguments

- Go to <https://www.stadtwerke-huerth.de/de/Muellkalender/Muellkalender.html> and select your location on the left of the calendar (not the dropdown menu above the calendar).
- Copy the link of the button `Termine herunterladen` below the calendar.
- Replace the `url` in the example configuration with this link.
- You may want to change the date in the url to `{%Y}-01-01` für multi year use (not sure if necessary)

## Examples

### Alt-Hürth Am Römerkanal

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        url: https://www.swhmobil.de/muellkalender?tx_swhtonnenalarm_pi1%5Baction%5D=calendarFile&tx_swhtonnenalarm_pi1%5Bcontroller%5D=Calendar&tx_swhtonnenalarm_pi1%5BselectedDate%5D={%Y}-01-01&tx_swhtonnenalarm_pi1%5BselectedDistrict%5D=Alt-H%C3%BCrth&tx_swhtonnenalarm_pi1%5BselectedStreet%5D=Am%20R%C3%B6merkanal&tx_swhtonnenalarm_pi1%5BselectedTypes%5D%5B0%5D=1&tx_swhtonnenalarm_pi1%5BselectedTypes%5D%5B1%5D=5&tx_swhtonnenalarm_pi1%5BselectedTypes%5D%5B2%5D=4&tx_swhtonnenalarm_pi1%5BselectedTypes%5D%5B3%5D=2&tx_swhtonnenalarm_pi1%5BselectedTypes%5D%5B4%5D=6&tx_swhtonnenalarm_pi1%5BselectedTypes%5D%5B5%5D=3&tx_swhtonnenalarm_pi1%5BselectedTypes%5D%5B6%5D=7&type=1985&cHash=21e359062f8252efaa7b3dbfc57b98c1
```
