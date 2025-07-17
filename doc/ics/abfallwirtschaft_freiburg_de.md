# Abfallwirtschaft Freiburg

Abfallwirtschaft Freiburg is supported by the generic [ICS](/doc/source/ics.md) source. For all available configuration options, please refer to the source description.


## How to get the configuration arguments

- Go to <https://www.abfallwirtschaft-freiburg.de/de/private_haushalte/abfuhrtermine.php> and select your location.
- Right-click on `ICS` and copy link address.
- Replace the `url` in the example configuration with this link.
- Replace the **2** year fields in the url with `{%Y}`.

## Examples

### Ahornweg

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        url: https://api.abfall.io/?key=ba5c0a03ba41d81479797313161ced08&mode=export&idhousenumber=13&wastetypes=1146,627,17,1554,1802,1553&timeperiod={%Y}0101-{%Y}1231&type=ics
```
