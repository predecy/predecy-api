__getDataAvailability: Verfügbarkeit von Prognosedaten abrufen__

__URL__: https://datacenter.predecy.de/predecy-api/rest/data/getDataAvailability  
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
      * __unit_name (String)__: der Name der Unit
      * __unit_nr (String)__: eine beschreibene Nummer der Unit (z.B. Artikelnummer)
      * __units_of_unit (String)__: Die Einheit der Unit (z.B. kg, Liter, Stück)
      * __conversion_to_global_aggregation (Float)__: Konversionsfaktor, um das Ergebnis global aggregieren zu können 
    * __locations (JSON-Array)__: die verfügbaren Locations
      * __location_id (Integer)__: die Location-ID
      * __location_name (String)__: der Name der Location
      * __location_nr (String)__: eine beschreibende Nummer der Location
      * __country_code (String)__: der Ländercode
      * __postal_code (Float)__: die Postleitzahl
      * __lat (Float)__: Geokoordinate Latitude der Location (WGS84)
      * __lng (Float)__: Geokoordinate Longitude der Location (WGS84)
    * __event_customers (JSON-Array)__: die Event-Customers, für die Ergebnisse vorliegen
      * __event_customer_id (Integer)__: die Event-Customer-ID
      * __event_customer_name (String)__: der Name des Event-Customers
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
                    "unit_id": 693,
                    "unit_name": "Produkt A",
                    "unit_nr": "18432",
                    "units_of_unit": "Stück",
                    "conversion_to_global_aggregation": 1.0
                }
            ],
            "locations": [
                {
                    "location_id": 996,
                    "location_name": "Stuttgart",
                    "location_nr": "H7B3",
                    "country_code": "DE",
                    "postal_code": "70176.0",
                    "lat": 48.78,
                    "lng": 9.18
                }
            ],
            "event_customers": [
                {
                    "event_customer_id": 492,
                    "event_customer_name": "Curcuma Solutions GmbH",
                    "key": "16543"
                },
                {
                    "event_customer_id": 753,
                    "event_customer_name": "Basil KG",
                    "key": "28753"
                }
            ]
       }
  }
  ```
  
  