## PREDECY API Dokumentation v2: setEvents

__1. Anlegen von Events__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/setEvents
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
* __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
* __events (JSON-Array)__: die Events, welche neu angelegt werden sollen
    * __event_type_description_id (Integer)__: die Event-Type-Description-ID
    * __client_id (Intege)__: die Client-ID für den abgefragten _API-Key_
    * __amount (Float)__: der Wert für den Event

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "events": [
        {
            "event_type_description_id": 1,
            "client_id": 17553,
            "amount": 115391.28860907062
        }
    ]
  }
  ```
  
__Response__:
* __events (JSON-Array)__: die Events, welche neu angelegt wurden
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

  __2. Updaten bestehender Locations__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/setEvents
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
* __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
* __events (JSON-Array)__: die Events, welche aktualisiert werden sollen
    * __event_id (String)__: die ID des Events als Primärschlüssel
    * __event_type_description_id (Integer)__: die Event-Type-Description-ID
    * __client_id (Intege)__: die Client-ID für den abgefragten _API-Key_
    * __amount (Float)__: der Wert für den Event

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "events": [
        {
            "event_id": "3619228",
            "event_type_description_id": 1,
            "client_id": 17553,
            "amount": 22999.3
        }
    ]
  }
  ```
  
__Response__:
 * __events (JSON-Array)__: die Events, welche neu angelegt wurden
    * __event_id (String)__: die ID des aktualisierten Events als Primärschlüssel
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
                "amount": 22999.3
            }
        ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
