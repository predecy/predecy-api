## PREDECY API Dokumentation: setEvents

__1. Anlegen von Events__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/setEvents
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
* __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
* __events (JSON-Array)__: die Events, welche neu angelegt werden sollen
    * __location_id (Integer)__: location_id, wo Event stattgefunden hat
    * __unit_id (Integer)__: unit_id, die verkauft/gemessen wurde
    * __event_type_description_id (Integer)__: Art des Events 
                *  0 = Messdaten
                *  1 = Prognosen
                *  2 = Prognosen, nicht aktuell 
                * 11 = Validierung
                * 12 = Validierung, nicht aktuell
                * 21 = Messdaten, nicht aktuell
    * **__event_customer_id (Integer) _optional_**: event_customer_id, Id des Customers
    * __amount (Float)__: der Wert für den Event
    * __date_of_event (DateTime)__: das Datum des Ereignisses, retrospektiv oder prognostisch
    * **date_of_prediction (DateTime)_optional_**: das Datum an dem die Prognose gemacht wurde

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "events": 
        
            [
  {
    
    "location_id" : 4037,
    "unit_id" : 76663,
    "event_type_description_id" : 0,
    "event_customer_id" : 29435,
    "date_of_event" : "2013-01-01 00:00:00",
    "date_of_prediction" : null,
    "amount" : 0,
    "uncertainty_of_amount_by_model" : null,
    "uncertainty_of_amount_by_features" : null
  }
        
    ]
  }
  ```
  
__Response__:
* __events (JSON-Array)__: die Events, welche neu angelegt wurden
    * __event_id (String)__: die ID des Events als Primärschlüssel
    * __client_id (Intege)__: die Client-ID für den abgefragten _API-Key_
    * __amount (Float)__: der Wert für den Event
    * __date_of_event (DateTime)__: das Datum des Ereignisses
  
  Beispiel: 
  ```
  {
      "events": [
            {
                "event_id": "3619228",
                "client_id": 17553,
                "amount": 115391.28860907062,
                "date_of_event": "2019-07-20T00:00"
            }
        ]
  }
  ```


__2. Updaten bestehender Events__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/setEvents
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
* __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
* __events (JSON-Array)__: die Events, welche aktualisiert werden sollen
    * __event_id (String)__: die ID des Events als Primärschlüssel
    * __client_id (Intege)__: die Client-ID für den abgefragten _API-Key_
    * __amount (Float)__: der Wert für den Event
    * __date_of_event (DateTime)__: das Datum des Ereignisses

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "events": [
        {
            "event_id": "3619228",
            "client_id": 17553,
            "amount": 22999.3,
            "date_of_event": "2019-07-20T00:00"
        }
    ]
  }
  ```
  
__Response__:
 * __events (JSON-Array)__: die Events, welche neu angelegt wurden
    * __event_id (String)__: die ID des aktualisierten Events als Primärschlüssel
    * __client_id (Intege)__: die Client-ID für den abgefragten _API-Key_
    * __amount (Float)__: der Wert für den Event
    * __date_of_event (DateTime)__: das Datum des Ereignisses
  
  Beispiel: 
  ```
  {
      "events": [
            {
                "event_id": "3619228",
                "client_id": 17553,
                "amount": 22999.3,
                "date_of_event": "2019-07-20T00:00"
            }
        ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
