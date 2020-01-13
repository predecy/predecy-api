## PREDECY API Dokumentation v2: setLocations

__1. Anlegen von Locations__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/setUnits 
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
      * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
      * __locations (JSON-Array)__: die Locations, welche neu angelegt werden sollen
        * **name (Integer) _optional_**: der Name der Location
        * **location_nr (String) _optional_**: eine beschreibende Nummer der Location
        * __country_code (String)__: der Ländercode
        * __postal_code (Float)__: die Postleitzahl
        * __lat (Float)__: Geokoordinate Latitude der Location (WGS84)
        * __lng (Float)__: Geokoordinate Longitude der Location (WGS84)

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "locations": [
        {
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
  
__Response__:
  * __locations (JSON-Array)__: die Locations, welche neu angelegt wurden
      * __location_id (Integer)__: die neue Location-ID (wird vom System automatisch vergeben)
      * __location_name (Integer)__: der Name der Location
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
              "location_name": "Stuttgart",
              "location_nr": "H7B3",
              "country_code": "DE",
              "postal_code": "70176.0",
              "lat": 48.78,
              "lng": 9.18
          }
      ]
  }
  ```

  __1. Updaten bestehender Units__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/setUnits 
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
      * __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
      * __locations (JSON-Array)__: die Locations, welche aktualisiert werden sollen
        * __location_id (Integer)__: die Location-ID
        * **location_name (Integer) _optional_**: der Name der Location
        * **location_nr (String) _optional_**: eine beschreibende Nummer der Location
        * **country_code (String) _optional_**: der Ländercode
        * **postal_code (Float) _optional_**: die Postleitzahl
        * **lat (Float) _optional_**: Geokoordinate Latitude der Location (WGS84)
        * **lng (Float) _optional_**: Geokoordinate Longitude der Location (WGS84)

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "locations": [
        {
            "location_id": 1,
            "location_name": "Stuttgart 1"
        }
    ]
  }
  ```
  
__Response__:
  * __locations (JSON-Array)__: die Locations, welche neu angelegt wurden
      * __location_id (Integer)__: die aktualisierte Location-ID
      * __location_name (Integer)__: der Name der Location
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
              "location_name": "Stuttgart 1",
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
  