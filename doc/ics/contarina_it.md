# Contarina S.p.A

Contarina S.p.A is supported by the generic [ICS](/doc/source/ics.md) source. For all available configuration options, please refer to the source description.


## How to get the configuration arguments

- Copy the `url` in the example configuration with this link.
- Replace the url's `{zone}` substring with your location's zone code (check below for the chart)
- Keeping `regex` and `split_at` as they are will remove potetially unnecessary names and split the waste types if there are multiple in one day.

Zone codes `{code} : {zone}`:
  - 1 : "Treviso - cintura urbana",
  - 2 : "Treviso - fuori mura",
  - 3 : "Treviso - centro storico",
  - 4 : "Arcade",
  - 5 : "Breda di Piave",
  - 6 : "Carbonera",
  - 7 : "Casale sul Sile",
  - 8 : "Casier",
  - 9 : "Giavera del Montello",
  - 10 : "Maserada sul Piave",
  - 11 : "Monastier di Treviso",
  - 12 : "Morgano",
  - 13 : "Nervesa della Battaglia",
  - 14 : "Paese",
  - 15 : "Ponzano Veneto",
  - 16 : "Povegliano",
  - 17 : "Preganziol",
  - 18 : "Quinto di Treviso",
  - 19 : "Roncade",
  - 20 : "San Biagio di Callalta",
  - 21 : "Silea",
  - 22 : "Spresiano",
  - 23 : "Susegana",
  - 24 : "Villorba",
  - 25 : "Volpago del Montello",
  - 26 : "Zenson di Piave",
  - 27 : "Zero Branco",
  - 28 : "Altivole",
  - 29 : "Asolo - centro storico",
  - 30 : "Asolo - fuori centro storico",
  - 31 : "Borso del Grappa",
  - 32 : "Caerano di San Marco",
  - 33 : "Castelcucco",
  - 34 : "Castelfranco Veneto - centro storico",
  - 35 : "Castelfranco Veneto - fuori centro storico",
  - 36 : "Castello di Godego",
  - 37 : "Cavaso del Tomba",
  - 38 : "Cornuda",
  - 40 : "Crocetta del Montello",
  - 41 : "Fonte",
  - 42 : "Istrana",
  - 43 : "Loria",
  - 44 : "Maser",
  - 45 : "Monfumo",
  - 46 : "Montebelluna - centro storico",
  - 47 : "Montebelluna - fuori centro storico",
  - 49 : "Pederobba",
  - 50 : "Possagno",
  - 51 : "Resana",
  - 52 : "Riese Pio X",
  - 53 : "San Zenone degli Ezzelini",
  - 54 : "Trevignano",
  - 55 : "Vedelago",
  - 56 : "Pieve del Grappa"

## Examples

### Treviso - cintura urbana"

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        regex: '.*: (.*)'
        split_at: ', '
        url: https://contarina.it/ajax/moduli/appbugfixapi/genera_ics_calendari?id_zona=1
```
