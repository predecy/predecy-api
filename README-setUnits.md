## PREDECY API Dokumentation v2: setUnits

__1. Anlegen von Units__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/setUnits 
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
      * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
      * __units (JSON-Array)__: die Units, welche neu angelegt werden sollen
        * __unit_name (String)__: der Name der Unit
        * __unit_nr (String)__: eine beschreibene Nummer der Unit (z.B. Artikelnummer)
        * __units_of_unit (String)__: Die Einheit der Unit (z.B. kg, Liter, Stück)
        * __conversion_to_global_aggregation (Float)__: Konversionsfaktor, um das Ergebnis global aggregieren zu können 

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "units": [
		{
			"unit_name": "Produkt A",
		    "unit_nr": "18432",
		    "units_of_unit": "Stück",
		    "conversion_to_global_aggregation": 1.0
		}
    ]
  }
  ```
  
__Response__:
  * __units (JSON-Array)__: die Units, welche neu angelegt wurden
      * __unit_id (Integer)__: die neue Unit-ID (wird vom System automatisch vergeben)
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

  __1. Updaten bestehender Units__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/setUnits 
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
      * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
      * __units (JSON-Array)__: die Units, welche aktualisiert werden sollen
        * __unit_id (Integer)__: die Unit-ID, welche aktualisiert werden sollen
        * **unit_name (String) _optional_**: der Name der Unit, falls dieser Wert aktualisiert werden soll
        * **unit_nr (String) _optional_**: eine beschreibene Nummer der Unit (z.B. Artikelnummer), falls dieser Wert aktualisiert werden soll
        * **units_of_unit (String) _optional_**: Die Einheit der Unit (z.B. kg, Liter, Stück), falls dieser Wert aktualisiert werden soll
        * **conversion_to_global_aggregation (Float) _optional_**: Konversionsfaktor, um das Ergebnis global aggregieren zu können, falls dieser Wert aktualisiert werden soll

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "units": [
		{
            "unit_id": 693,
			"unit_name": "Produkt AA"
		}
    ]
  }
  ```
  
__Response__:
  * __units (JSON-Array)__: die Units, welche aktualisiert wurden
      * __unit_id (Integer)__: die aktualisierte Unit-ID
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
              "unit_name": "Produkt AA",
              "unit_nr": "18432",
              "units_of_unit": "Stück",
              "conversion_to_global_aggregation": 1.0
          }
      ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  