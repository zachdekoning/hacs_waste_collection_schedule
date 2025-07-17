# C-Trace.de

Support for schedules provided by [c-trace.de](https://www.c-trace.de) which is servicing multiple municipalities.

## Configuration via configuration.yaml

```yaml
waste_collection_schedule:
  sources:
    - name: c_trace_de
      args:
        service: SERVICE
        ort: ORT
        gemeinde: GEMEINDE
        ortsteil: ORTSTEIL
        strasse: STRASSE
        hausnummer: HAUSNUMMER
        abfall: ABFALLARTEN
```

### Configuration Variables

**service**
*(string) (required)*
Name of the service which is specific to your municipality. See the table below to get the right value for your location.

**ort**
*(string) (optional)*
Needed for most municipalities but no all

**gemeinde**
*(string) (optional)*
Needed for some municipalities but not all (can be left empty if same as `ort` or unneeded)

**ortsteil**
*(string) (optional)*
Needed only for some municipalities but not all (can be left empty if unneeded)

**strasse**
*(string) (required)*

**hausnummer**
*(string) (required)*

**abfall**
*(string) (optional)*
Needed only to filter waste types (if empty you get all waste types). Separator between waste types is '|'.

## Example

```yaml
waste_collection_schedule:
  sources:
  - name: c_trace_de
    args:
      ort: Riedstadt
      ortsteil: Crumstadt
      strasse: Am Lohrrain
      hausnummer: 3
      service: grossgeraulandkreis-abfallkalender
```

```yaml
waste_collection_schedule:
  sources:
    - name: c_trace_de
      args:
        service: bremenabfallkalender
        ort: Bremen
        strasse: Abbentorstraße
        hausnummer: 5
```

```yaml
waste_collection_schedule:
  sources:
  - name: c_trace_de
    args:
      strasse: Am Kindergarten
      hausnummer: 1
      service: landau
```

```yaml
waste_collection_schedule:
  sources:
  - name: c_trace_de
    args:
      strasse: Am Reidigermeer
      hausnummer: 2d/e
      service: aurich-abfallkalender
      gemeinde: Aurich
      ort: Kirchdorf
```

## How to get the source arguments

This source requires the name of a `service` which is specific to your municipality. Use the following map to get the right value for your district.

<!--Begin of service section-->
|Municipality|service|
|-|-|
| Abfallwirtschaft Rheingau-Taunus-Kreis | `rheingauleerungen` |
| Abfallwirtschaftsbetrieb Landkreis Augsburg | `augsburglandkreis` |
| Abfallwirtschaftsbetrieb Landkreis Aurich | `aurich-abfallkalender` |
| Abfallwirtschaftsverband Kreis Groß-Gerau | `grossgeraulandkreis-abfallkalender` |
| Bau & Service Oberursel | `oberursel` |
| Bremer Stadtreinigung | `bremenabfallkalender` |
| Entsorgungs- und Wirtschaftsbetrieb Landau in der Pfalz | `landau` |
| Kreisstadt Dietzenbach | `dietzenbach` |
| Kreisstadt St. Wendel | `stwendel` |
| Landkreis Roth | `roth` |
| Landratsamt Main-Tauber-Kreis | `maintauberkreis-abfallkalender` |
| Stadt Arnsberg | `arnsberg-abfallkalender` |
| Stadt Bayreuth | `bayreuthstadt-abfallkalender` |
| Stadt Overath | `overathabfallkalender` |
| WZV Kreis Segeberg | `segebergwzv-abfallkalender` |
<!--End of service section-->

## Tip

If your waste-service has an online-tool where you can get an ical or CSV-File, you can extract the needed `service` from the URL of the files.
![image](https://user-images.githubusercontent.com/2480235/210091450-663907b0-6a9c-45b4-b0ae-00110896bb08.png)


Link for above image: https://web.c-trace.de/segebergwzv-abfallkalender/(S(ebi2zcbvfeqp0za3ofnepvct))/abfallkalender/cal/2023?Ort=Bad%20Segeberg&Strasse=Am%20Wasserwerk&Hausnr=2&abfall=0|1|2|3|4|5|6|7|

From this Link you can extract the following parameters:

`web|app`.c-trace.de/`(web.)service`/some-id/abfallkalender/`cal|downloadcal` `/year|`?Ort=`ort`&Ortsteil=`ortsteil`&Strasse=`strasse`&Hausnr=`hausnummer`&abfall='abfallarten'...
