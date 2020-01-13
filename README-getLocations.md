## PREDECY API Dokumentation v2: getLocations

__Locations abfragen__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/getLocations
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
  * __locations (JSON-Array)__: die Locations, welche mit der Client-ID für den abgefragten _API-Key_ verknüpft sind
      * __location_id (Integer)__: die Location-ID
      * __name (Integer)__: der Name der Location
      * __location_nr (String)__: eine beschreibende Nummer der Location
      * __country_code (String)__: der Ländercode
      * __postal_code (Float)__: die Postleitzahl
      * __lat (Float)__: Geokoordinate Latitude der Location (WGS84)
      * __lng (Float)__: Geokoordinate Longitude der Location (WGS84)
  
  Beispiel: 
  ```
  {
      "locations": [
          {
              "location_id": 1,
              "name": "Stuttgart",
              "location_nr": "H7B3",
              "country_code": "DE",
              "postal_code": "70176.0",
              "lat": 48.78,
              "lng": 9.18
          }
      ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  