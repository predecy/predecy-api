## PREDECY API Dokumentation v2

Die PREDECY API ist eine REST-API, welche zum Lesen von Prognoseergebnissen folgende Methoden unterstützt:

__1. Verfügbarkeit von Prognosedaten abrufen__

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
                    "name": "Produkt A"
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
  
  
  
__2. Prognosedaten abfragen__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/getData 
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
  * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
  * **event_type_description_id (Integer) _optional_**: Auswahl der Ergebnisse nach Event-Type-Description-ID; 1: Prognose (default), 11: Validierung
  * **event_customer_id (Integer) _optional_**: Filter nach Event-Customer-ID; 0 für alle verfügbaren Event-Customer-IDs (default)
  * **unit_id (Integer) _optional_**: Filter nach Unit-Id; 0 für alle verfügbaren Unit-IDs (default)
  * **location_id (Integer) _optional_**: Filter nach Location-Id; 0 für alle verfügbaren Location-IDs (default)
  * **limit (Integer) _optional_**: Anzahl der Ergebnisse beschränken (0 < limit <= 10000); default ist 10000
  * **offset (Integer) _optional_**: Offset, um weitere _limit_ Ergebnisse abzufrufen (offset >= 0; default ist 0 

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",
    "event_type_description_id": 1,
    "event_customer_id": 1,
    "unit_id": 1,
    "location_id": 1,
    "limit": 1,
    "offset": 0
  }
  ```
  
__Response__:
  * __input (JSON-Objekt)__: der Input der Abfrage inklusive der gesetzten Default-Werte
    * __event_type_description_id (Integer)__: gewählte Event-Type-Description-ID
    * __event_customer_id (Integer)__: gewählter Filter nach Event-Customer-ID
    * __unit_id (Integer)__: gewählter Filter nach Unit-Id
    * __location_id (Integer)__: gewählter Filter nach Location-Id
    * __limit (Integer)__: gewählte Beschränktung der Ergebnisanzahl
    * __offset (Integer)__: gewählter Offset
  * __result_count (Integer)__: Anzahl der Ergebnisse
  * __result (JSON-Array)__: die Ergebnisse als Liste
      * __event_id (String)__: die ID des Events als Primärschlüssel
      * __client_id (Intege)__: die Client-ID für den abgefragten _API-Key_
      * __location_id (Integer)__: die Location-ID für das Ergebnis
      * __unit_id (Integer)__: die Unit-ID für das Ergebnis
      * __event_type_description_id (Integer)__: die Event-Type-Description-ID für das Ergebnis
      * __event_customer_id (Integer)__: die Event-Customer-ID für das Ergebnis
      * __date_of_event (DateTime)__: das Datum des Ereignisses, an dem das Ergebnis Gültigkeit hat
      * __date_of_prediction (DateTime)__: das Datum der Berechnung der Vorhersage
      * __amount (Float)__: der berechnete Ergebniswert
      * __uncertainty_of_amount_by_model (Float)__: die Unsicherheit des berechneten Ergebniswerts durch das Modell
      * __uncertainty_of_amount_by_features (Float)__: die Unsicherheit des berechneten Ergebniswerts durch die Features
      * __unit_nr__: eine beschreibene Nummer der Unit (z.B. Artikelnummer)
      * __name__: der Name der Unit
      * __metadata__: optionale Metadaten
      * __units_of_unit__: Die Einheit der Unit (z.B. kg, Liter, Stück)
      * __conversion_to_global_aggregation__: Konversionsfaktor, um das Ergebnis global aggregieren zu können
      * __lat (Float)__: Geokoordinate Latitude der Location (WGS84)
      * __lng (Float)__: Geokoordinate Longitude der Location (WGS84)
      * __location_nr (String)__: eine beschreibende Nummer der Location
      * __postal_code (Float)__: die Postleitzahl
      * __event_customer_id (Integer)__: die Event-Customer-ID
      * __country_code (String)__: der Ländercode
      * __key (String)__: ein Key zur spezifischen Beschreibung des Event-Customers (z.B. Kundennummer)
  
  Beispiel: 
  ```
  {
      "input": {
          "event_type_description_id": 1,
          "limit": 10000,
          "offset": 0,
          "event_customer_id": 1,
          "unit_id": 1,
          "location_id": 1
      },
      "result_count": 1,
      "result": [
          {
              "event_id": "3619228",
              "client_id": 1,
              "location_id": 1,
              "unit_id": 1,
              "event_type_description_id": 1,
              "event_customer_id": 1,
              "date_of_event": "2019-07-20T00:00",
              "date_of_prediction": "2019-07-15T13:50:56",
              "amount": 115391.28860907062,
              "uncertainty_of_amount_by_model": 7260.369419546308,
              "uncertainty_of_amount_by_features": 0.0,
              "unit_nr": "1",
              "name": "Produkt A",
              "metadata": null,
              "units_of_unit": "Stück",
              "conversion_to_global_aggregation": 1.0,
              "lat": 48.78,
              "lng": 9,18,
              "location_nr": null,
              "postal_code": "70176.0",
              "country_code": "DE",
              "key": "16543"
          }
      ]
  }
  ```
  
  
  
  
[Impressum](https://www.spicetech.de/#Impressum)
