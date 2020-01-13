## PREDECY API Dokumentation: getData

__Prognosedaten abfragen__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/getData 
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
  * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
  * **event_type_description_id (Integer) _optional_**: Auswahl der Ergebnisse nach Event-Type-Description-ID; 1: Prognose (default), 11: Validierung
  * **limit (Integer) _optional_**: Anzahl der Ergebnisse beschränken (0 < limit <= 10000); default ist 10000
  * **offset (Integer) _optional_**: Offset, um weitere _limit_ Ergebnisse abzufrufen (offset >= 0; default ist 0 
  * **event_customer_id (Integer) _optional_**: Filter nach Event-Customer-ID; 0 für alle verfügbaren Event-Customer-IDs (default)
  * **unit_id (Integer) _optional_**: Filter nach Unit-Id; 0 für alle verfügbaren Unit-IDs (default)
  * **location_id (Integer) _optional_**: Filter nach Location-Id; 0 für alle verfügbaren Location-IDs (default)
  

  Beispiel:  
  ```
  {
     "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",
     "event_type_description_id": 1,
     "limit": 10000,
     "offset": 0,
     "event_customer_id": 492,
     "unit_id": 693,
     "location_id": 996
  }
  ```
  
__Response__:
  * __input (JSON-Objekt)__: der Input der Abfrage inklusive der gesetzten Default-Werte
    * __event_type_description_id (Integer)__: gewählte Event-Type-Description-ID
    * __limit (Integer)__: gewählte Beschränktung der Ergebnisanzahl
    * __offset (Integer)__: gewählter Offset
    * __event_customer_id (Integer)__: gewählter Filter nach Event-Customer-ID
    * __unit_id (Integer)__: gewählter Filter nach Unit-Id
    * __location_id (Integer)__: gewählter Filter nach Location-Id
  * __result_count (Integer)__: Anzahl der Ergebnisse
  * __result (JSON-Array)__: die Ergebnisse als Liste
      * __event_id (String)__: die ID des Events als Primärschlüssel
      * __event_type_description_id (Integer)__: die Event-Type-Description-ID für das Ergebnis
      * __client_id (Intege)__: die Client-ID für den abgefragten _API-Key_
      * __amount (Float)__: der berechnete Ergebniswert
      * __uncertainty_of_amount_by_model (Float)__: die Unsicherheit des berechneten Ergebniswerts durch das Modell
      * __uncertainty_of_amount_by_features (Float)__: die Unsicherheit des berechneten Ergebniswerts durch die Features
      * __date_of_event (DateTime)__: das Datum des Ereignisses, an dem das Ergebnis Gültigkeit hat
      * __date_of_prediction (DateTime)__: das Datum der Berechnung der Vorhersage
      * __location_id (Integer)__: die Location-ID für das Ergebnis
      * __location_name (Integer)__: der Name der Location für das Ergebnis
      * __location_nr (String)__: eine beschreibende Nummer der Location
      * __country_code (String)__: der Ländercode
      * __postal_code (Float)__: die Postleitzahl
      * __lat (Float)__: Geokoordinate Latitude der Location (WGS84)
      * __lng (Float)__: Geokoordinate Longitude der Location (WGS84)
      * __unit_id (Integer)__: die Unit-ID für das Ergebnis
      * __unit_name (String)__: der Name der Unit
      * __unit_nr (String)__: eine beschreibene Nummer der Unit (z.B. Artikelnummer)
      * __units_of_unit (String)__: Die Einheit der Unit (z.B. kg, Liter, Stück)
      * __conversion_to_global_aggregation (Float)__: Konversionsfaktor, um das Ergebnis global aggregieren zu können 
      * __event_customer_id (Integer)__: die Event-Customer-ID für das Ergebnis
      * __event_customer_name (String)__: der Name des Event-Customers
      * __key (String)__: ein Key zur spezifischen Beschreibung des Event-Customers (z.B. Kundennummer)
  
  Beispiel: 
  ```
  {
      "input": {
          "event_type_description_id": 1,
          "limit": 10000,
          "offset": 0,
          "event_customer_id": 492,
          "unit_id": 693,
          "location_id": 996
      },
      "result_count": 1,
      "result": [
          {
              "event_id": "3619228",
              "event_type_description_id": 1,
              "client_id": 17553,
              "amount": 115391.28860907062,
              "uncertainty_of_amount_by_model": 7260.369419546308,
              "uncertainty_of_amount_by_features": 0.0,
              "date_of_event": "2019-07-20T00:00",
              "date_of_prediction": "2019-07-15T13:50:56",
              "location_id": 1,
              "location_name": "Stuttgart",
              "location_nr": "H7B3",
              "country_code": "DE",
              "postal_code": "70176.0",
              "lat": 48.78,
              "lng": 9.18,
              "unit_id": 693,
              "unit_name": "Produkt A",
              "unit_nr": "18432",
              "units_of_unit": "Stück",
              "conversion_to_global_aggregation": 1.0,
              "event_customer_id": 492,
              "event_customer_name": "Curcuma Solutions GmbH",
              "key": "16543"  
          }
      ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
