## PREDECY API Dokumentation: getUnits

__Units abfragen__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/getUnits
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
  * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung

  Beispiel:  
  ```
  {
     "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003"
  }
  ```
  
__Response__:
  * __units (JSON-Array)__: die Units, welche mit der Client-ID für den abgefragten _API-Key_ verknüpft sind
      * __unit_id (Integer)__: die Unit-ID
      * __unit_name (String)__: der Name der Unit
      * __unit_nr (String)__: eine beschreibene Nummer der Unit (z.B. Artikelnummer)
      * __units_of_unit (String)__: Die Einheit der Unit (z.B. kg, Liter, Stück)
      * __conversion_to_global_aggregation (Float)__: Konversionsfaktor, um das Ergebnis global aggregieren zu können 
  
  Beispiel: 
  ```
  {
      "units": [
          {
              "unit_id": 693,
              "unit_name": "Produkt A",
              "unit_nr": "18432",
              "units_of_unit": "Stück",
              "conversion_to_global_aggregation": 1.0
          }
      ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
