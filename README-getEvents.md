## PREDECY API Dokumentation v2: getEvents

__Events abfragen__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/getEvents  
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
  * __events (JSON-Array)__: die Events, welche mit der Client-ID für den abgefragten _API-Key_ verknüpft sind
      * __event_id (String)__: die ID des Events als Primärschlüssel
      * __event_type_description_id (Integer)__: die Event-Type-Description-ID
      * __client_id (Intege)__: die Client-ID für den abgefragten _API-Key_
      * __amount (Float)__: der Wert für den Event
      * __date_of_event (DateTime)__: das Datum des Ereignisses
  
  Beispiel: 
  ```
  {
      "events": [
          {
            "event_id": "3791919",
            "location_id": 49,
            "unit_id": 27,
            "event_customer_id": 105,
            "uncertainty_of_amount_by_model": null,
            "uncertainty_of_amount_by_features": null,
            "date_of_event": "2013-01-01T00:00",
            "amount": 22998.3
          }
      ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
