## PREDECY API Dokumentation v2: getEvents

__Events abfragen__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/getEvents
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
  
  Beispiel: 
  ```
  {
      "events": [
          {
              "event_id": "3619228",
              "event_type_description_id": 1,
              "client_id": 17553,
              "amount": 115391.28860907062
          }
      ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  