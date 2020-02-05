## PREDECY API Dokumentation: getPrivateDataTypes

__1. Abfragen von PrivateDataTypes__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/getPrivateDataTypes  
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
  * __private_data_types (JSON-Array)__: die privateDataTypes, welche neu angelegt wurden
      * __private_data_type_id (Integer)__: die neue PrivateDataType-ID (wird vom System automatisch vergeben)
      * __name (String)__: Name der PrivateData, z.B. Marketing
      * __unit (String)__: Einheit der Private Data, z.B. Euro, wenn eine Marketingaktion einen Preis betrifft
    
  
  Beispiel: 
```
  {
    "private_data_types": [
        {
            "private_data_type_id": 11,
            "name": "werbeaktion",
            "unit": "€"
        }
    ]
}
```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
