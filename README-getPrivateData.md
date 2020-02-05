## PREDECY API Dokumentation: getPrivateData

__1. Abfragen von PrivateData__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/getPrivateData: 
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
  * __private_data (JSON-Array)__: die privateData
      * __private_data_id (Integer)__: ID der private Data
      * __private_data_type_id (Integer)__: PrivateDataType-ID, z.B. ID von zugehöriger Werbeaktion 
      * __value (Float)__: Wert, z. B. Anzahl oder Preis, etc. 
      * __private_date (Datetime)__: Datum, an dem der Wert der private Data gilt
      * **uncertainty_of_value (Float), _optional_**: Unsicherheit, mit dem der Wert belastet ist
      * **event_customer_id (Integer), _optional_**: Event-Customer-ID der Kunden, für die die private Data (z.B. Marketingaktion) gilt
      * **event_customer_id (Integer), _optional_**: Unit-ID des Produkts, für die die private Data (z.B. Marketingaktion, Preisnachlass) gilt
    
  
  Beispiel: 
```
  {
    "private_data": [
        {
            "private_data_id": 192495,
            "private_data_type_id": 11,
            "value": 5.0,
            "private_date": "2019-08-01",
            "uncertainty_of_value": 0.0,
            "event_customer_id": 105,
            "unit_id": 27
        }
    ]
}
```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
