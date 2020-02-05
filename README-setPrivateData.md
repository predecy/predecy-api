## PREDECY API Dokumentation: setPrivateData

__1. Anlegen von PrivateData__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/setPrivateData   
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
  * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
  * __private_data (JSON-Array)__: neu anzulegende privateData (z.B. Preisreduktion, Marketing, etc.)
    * __private_data_type_id (Integer)__: privateDataType-ID, die für die private Data verwendet wird (siehe  __README-setPrivateDataTypes.md__)
    * __value (Float)__: Wert, der privateData, z.B. Anzahl, oder Preis 
    * **unit_id (Integer), _optional_**: Unit-ID, für die die private Data gilt
    * **event_customer_id (Integer), _optional_**: Kunden-ID, für den die Marketing-/Preisaktion gilt (kann auch für alle gelten)
  

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",

    "private_data": [
        {
            "private_data_type_id": 11,
            "value": 5,
            "private_date": "2019-10-18",
            "unit_id":27,
            "event_customer_id":105
        }
    ]
  }
  ```
  
__Response__:
  * __private_data (JSON-Array)__: die privateData
      * __private_data_id (Integer)__: ID der private Data (wird vom System automatisch vergeben)
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
            "private_date": "2019-10-18",
            "uncertainty_of_value": 0.0,
            "event_customer_id": 105,
            "unit_id": 27
        }
    ]
}
```

__2. Updaten bestehender PrivateData__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/setPrivateData   
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
  * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
  * __private_data (JSON-Array)__: privateData (z.B. Preisreduktion, Marketing, etc.), die geändert werden soll
    * __private_data_id (Integer)__:  privateData-ID, die geändert werden soll
    * __private_data_type_id (Integer)__: privateDataType-ID, die für die private Data verwendet wird (siehe  [README-setPrivateDataTypes.md](https://github.com/predecy/predecy-api/blob/master/README-setPrivateDataTypes.md))
    * __value (Float)__: Wert, der privateData, z.B. Anzahl, oder Preis 
    * **unit_id (Integer), _optional_**: Unit-ID, für die die private Data gilt
    * **event_customer_id (Integer), _optional_**: Kunden-ID, für den die Marketing-/Preisaktion gilt (kann auch für alle gelten)
  

Beispiel:
```
{
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",
    "private_data": [
        {
            "private_data_id": 192495,
            "private_data_type_id": 11,
            "value": 7.5,
            "private_date": "2019-10-18",
            "unit_id": 27
        }
    ]
}
```
__Response__:

 * __private_data (JSON-Array)__: privateData (z.B. Preisreduktion, Marketing, etc.), aktualisiert
    * __private_data_id (Integer)__:  privateData-ID, die geändert wurde
    * __private_data_type_id (Integer)__: privateDataType-ID, die für die private Data verwendet wurde (siehe [README-setPrivateDataTypes.md](https://github.com/predecy/predecy-api/blob/master/README-setPrivateDataTypes.md)), möglicherweise aktualisiert
    * __value (Float)__: Wert, der privateData, z.B. Anzahl, oder Preis, möglicherweise aktualisiert 
    * **unit_id (Integer), _optional_**: Unit-ID, für die die private Data gilt
    * **event_customer_id (Integer), _optional_**: Kunden-ID, für den die Marketing-/Preisaktion gilt (kann auch für alle gelten), möglicherweise aktualisiert

```
{
    "private_data": [
        {
            "private_data_id": 192495,
            "private_data_type_id": 11,
            "value": 7.5,
            "private_date": "2019-10-18",
            "unit_id": 27
        }
    ]
}
``` 
  
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
