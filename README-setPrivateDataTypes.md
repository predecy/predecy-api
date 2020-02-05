## PREDECY API Dokumentation: setPrivateDataTypes

__1. Anlegen von PrivateDataTypes__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/setPrivateDataType  
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
  * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
  * __private_data_types (JSON-Array)__: die privaten Daten (z.B. Promotionkalender), welche neu angelegt und im laufenden Betrieb berücksichtigt werden sollen
  * __name (String)__: eine beschreibener Name
  * **unit (String), _optional_**: Einheit der Private Data, z.B. Euro
    

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "private_data_types": [
		{
		    "unit": "€",
		    "name": "werbeaktion"
		}
    ]
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


__2. Updaten bestehender Units__
  
__URL__: https://datacenter.predecy.de/predecy-api/rest/data/setPrivateDataTypes   
__Method__: POST  
__Content-Type__: application/json   
__Body (Parameter als JSON-Objekt)__:
  * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
  * __private_data_types (JSON-Array)__: die privaten Daten (z.B. Werbeaktionen), die aktualisiert werden sollen 
    * __name (String)__: Name, der aktualisiert werden soll
    * **unit (Integer), _optional_**: Einheit der privaten Daten, z.B. Euro, Anzahl etc.
   

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
     "private_data_types": [
		{
            "private_data_type_id": 11,
            "name": "werbeaktion", 
            "unit": "anzahl"
		}
    ]
  }
  ```
  
__Response__:
  * __private_data_types (JSON-Array)__: private DataTypes, aktualisiert
      * __private_data_type_id (Integer)__: die aktualisierte privateDataType-ID
      * __name (String)__: der Name der privaten Daten
      * __unit (String)__: eine beschreibende Einheit, z.B. Euro, Anzahl
      
  
  Beispiel: 
  ```
  {
    "private_data_types": [
        {
            "private_data_type_id": 11,
            "name": "werbeaktion",
            "unit": "anzahl"
        }
    ]
}
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
