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
    * **event_customer_id (Integer), _optional_**: event_customer_id, Id des Kunden
    * __amount (Float)__: der Wert für den Event
    * __date_of_event (DateTime)__: das Datum des Events, retrospektiv oder prognostisch
    * **date_of_prediction (DateTime)_optional_**: das Datum, an dem die Prognose gemacht wurde
    * **uncertainty_of_amount_by_model (Float)_optional_**: Unsicherheit des Models
    * **uncertainty_of_amount_by_feature (Float)_optional_**: Unsicherheit des Features, z.B. Wettervorhersage

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "events": 
        
            [
  {
    "location_id" : 249,
    "unit_id" : 227,
    "event_customer_id" : 29435,
    "date_of_event" : "2013-01-01 00:00:00",
    "amount" : 103.45,
  }
        
    ]
  }
  ```
  
__Response__:
* __events (JSON-Array)__: die Events, welche neu angelegt wurden
    * __event_id (String)__: die ID des Events als Primärschlüssel
    * __unit_id (Integer)__: die ID der Unit, auf das sich das Event bezieht
    * __location_id (Integer)__: die Location-ID an dem der Event stattfindet
    * __amount (Float)__: der Wert für den Event
    * __date_of_event (DateTime)__: das Datum des Ereignisses
  
  Beispiel: 
  ```
  {
    "event": [
        {
            "event_id": 3791898,
            "location_id": 249,
            "unit_id": 227,
            "date_of_event": "2013-01-01",
            "amount": 103.45,
            "event_customer_id": 29435
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
    * __HINWEIS__: Beim Update eines Events muss beachtet werden, dass durch das Update ein Event neu anlegt wird und der bisherige (im unteren Beispiel event_id:3791898) archiviert wird. Dadurch werden auch Änderungen in der Datenbank verfolgt. Die Response bekommt von der Datenbank dann jeweils die letzte für das Event erstellte event_id. Beim Update können auch Pflichtfelder, wie location_id, unit_id sowie event_customer_id weggelassen werden. 

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "events": [
        {
            "event_id": 3791898,
            "location_id": 249,
            "unit_id": 227,
            "date_of_event": "2013-01-01",
            "amount": 22999.3,
            "event_customer_id": 29435
        }
    ]
  }
  ```
  
__Response__:
 * __events (JSON-Array)__: die Events, welche neu angelegt wurden
    * __event_id (Integer)__: die ID des aktualisierten Events als Primärschlüssel
    * __location_id (Integer)__: die Location-ID, an dem ein Event stattfindet
    * __unit_id (Integer)__: Unit-ID, für welche das Event gilt
    * __amount (Float)__: der Wert für den Event
    * __date_of_event (DateTime)__: das Datum des Events
  
  Beispiel: 
  ```
  {
      "events": [
            {
                "event_id": 3791912,
                "location_id": 249,
                "unit_id": 227,
                "date_of_event": "2013-01-01",
                "amount": 22999.3,
                "event_customer_id": 29435
            }
        ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
