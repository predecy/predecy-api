## PREDECY API Dokumentation v2

Die PREDECY API ist eine REST-API, welche zum Lesen von Prognoseergebnissen folgende Methoden unterstützt:

__1. Verfügbarkeit von Prognosedaten abrufen__

__URL__: https://api.predecy.de/predecy/getDataAvailability  
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
  * __api_key__: der API-Key zur Authentifizierung und Autorisierung

  Beispiel:  
  ```
  { "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003" }
  ```
  
__Response__:
  * __event_type_description_ids (JSON-Array)__: Liste der Ergebnisübersicht nach Event-Type-Description-ID
    * __event_type_description_id (Integer)__: die Event-Type-Description-ID für die Ergebnisse. (1: Prognose, 2: Validierung)
    * __count (Integer)__: die Anzahl der vorliegenden Ergebnisse für die Event-Type-Description-ID 
    * __date_min (Date)__: das untere Datum, für das Ergebnisse vorliegen
    * __date_max (Date)__: das obere Datum, für das Ergebnisse vorliegen
    * __units (JSON-Array)__: die verfügbaren Units
      * __unit_id (Integer)__: die Unit-ID
      * __name (String)__: der Name der  Unit
    * __locations (JSON-Array)__: die verfügbaren Locations
      * __location_id (Integer)__: die Location-ID
      * __name (String)__: der Name der Location
      * __lat (Float)__: Geokoordinate Latitude der Location (WGS84)
      * __lng (Float)__: Geokoordinate Longitude der Location (WGS84)
    * __event_customers (JSON-Array)__: die Event-Customers, für die Ergebnisse vorliegen
      * __event_customer_id (Integer)__: die Event-Customer-ID
      * __name (String)__: der Name des Event-Customers
      * __key (String)__: ein Key zur spezifischen Beschreibung des Event-Customers (z.B. Kundennummer)
  
  Beispiel: 
  ```
  {
    "event_type_description_ids": [
        {
            "event_type_description_id": 1,
            "count": 156,
            "date_min": "2019-07-20",
            "date_max": "2019-07-31",
            "units": [
                {
                    "unit_id": 1,
                    "name": "kg"
                }
            ],
            "locations": [
                {
                    "location_id": 1,
                    "name": "Stuttgart",
                    "lat": 48.78,
                    "lng": 9.18
                }
            ],
            "event_customers": [
                {
                    "event_customer_id": 1,
                    "name": "Curcuma Solutions GmbH",
                    "key": "16543"
                },
                {
                    "event_customer_id": 3,
                    "name": "Basil KG",
                    "key": "28753"
                }
            ]
       }
  }
  ```
