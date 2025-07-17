# Abfallwirtschaft Sonneberg

Abfallwirtschaft Sonneberg is supported by the generic [ICS](/doc/source/ics.md) source. For all available configuration options, please refer to the source description.


## How to get the configuration arguments

- Go to <https://www.abfallwirtschaft-sonneberg.de/abfallkalender/>.
- Select your municipality (`Ort`), district (`Ortsteil`) and - if necessary - street (`Straße`).
- Right-click each dropdown field an click `Inspect`. This will open your browser's developer tools and display the corresponding HTML source:

  ```html
    <!-- Some lines of code have been removed from the below for readability -->

    <select class="form-control" id="ort" name="ort">
        <option value="">Bitte Ort wählen</option>
        <option value="Föritztal">Föritztal</option>
        <option value="Neuhaus am Rennweg">Neuhaus am Rennweg</option>
        <option value="Sonneberg">Sonneberg</option>
    </select>

    <select class="form-control stadtteil" name="stadtteil" id="stadtteil">
        <option value="" selected=""></option>
        <option value="Bettelhecken">Bettelhecken (ab Bettelhecker Straße Nr. 57 und 66)</option>
        <option value="Hönbach">Hönbach</option>
        <option value="Innenstadtbereich">Innenstadtbereich</option>
        <option value="Steinbach">Steinbach (einschl. gesamte Bergstr.)</option>
    </select>

    <select class="form-control" name="strasse" id="strasse">
        <option value="" selected=""></option>
        <option value="Alte Molkerei">Alte Molkerei</option>
        <option value="Bettelhecker Straße bis Nr. 55 und 64">Bettelhecker Straße bis Nr. 55 und 64 (Coburger Allee bis Eisenbahnbrücke)</option>
    </select>
  ```

  You will need to get the exact `value` of your selected option as an option's value might differ from the text shown in the dropdown field for certain options, especially for the longer.
  
- Replace the corresponding `params` in the example configuration with your values.

  *Please note that there's usually no need to replace umlauts in parameter values with their respective Unicode number (e.g. `ä` -> `\xE4`).*
  *This just happens while generating this documentation from source.*
  *Refer to [Abfallwirtschaft Sonneberg's documentation source](/doc/ics/yaml/abfallwirtschaft_sonneberg_de.yaml) for unaltered examples.*

## Examples

### Föritztal, Schwärzdorf

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        method: POST
        params:
          ort: "F\xF6ritztal"
          stadtteil: "Schw\xE4rzdorf"
        url: https://www.abfallwirtschaft-sonneberg.de/PHPtoICS{%Y}.php
```
### Neuhaus am Rennweg, Neuhaus am Rennweg

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        method: POST
        params:
          ort: Neuhaus am Rennweg
          stadtteil: Neuhaus am Rennweg
        url: https://www.abfallwirtschaft-sonneberg.de/PHPtoICS{%Y}.php
```
### Sonneberg, Hönbach

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        method: POST
        params:
          ort: Sonneberg
          stadtteil: "H\xF6nbach"
        url: https://www.abfallwirtschaft-sonneberg.de/PHPtoICS{%Y}.php
```
### Sonneberg, Innenstadtbereich, Coburger Allee

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        method: POST
        params:
          ort: Sonneberg
          stadtteil: Innenstadtbereich
          strasse: Coburger Allee
        url: https://www.abfallwirtschaft-sonneberg.de/PHPtoICS{%Y}.php
```
### Sonneberg, Steinbach (einschl. gesamte Bergstr.)

```yaml
waste_collection_schedule:
  sources:
    - name: ics
      args:
        method: POST
        params:
          ort: Sonneberg
          stadtteil: Steinbach
        url: https://www.abfallwirtschaft-sonneberg.de/PHPtoICS{%Y}.php
```
