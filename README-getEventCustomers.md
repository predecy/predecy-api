## PREDECY API Dokumentation: getEventCustomers
__EventCustomers abfragen__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/getEventCustomers  
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
  * __event_customers (JSON-Array)__: die Event-Customers, welche mit der Client-ID für den abgefragten _API-Key_ verknüpft sind
      * __event_customer_id (Integer)__: die Event-Customer-ID
      * __name (String)__: der Name des Event-Customers
      * __key (String)__: ein Key zur spezifischen Beschreibung des Event-Customers (z.B. Kundennummer)
  
  Beispiel: 
  ```
  {
      "event_customers": [
          {
              "event_customer_id": 492,
              "name": "Curcuma Solutions GmbH",
              "key": "16543"  
          }
      ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
