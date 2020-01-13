## PREDECY API Dokumentation v2: setEventCustomers

__1. Anlegen von Event-Customers__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/setEventCustomers
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
* __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
* __event_customers (JSON-Array)__: die Event-Customers, welche neu angelegt werden sollen
    * __name (String)__: der Name des Event-Customers
    * __key (String)__: ein Key zur spezifischen Beschreibung des Event-Customers (z.B. Kundennummer)

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "event_customers": [
        {
            "name": "Curcuma Solutions GmbH",
            "key": "16543"  
        }
    ]
  }
  ```
  
__Response__:
* __event_customers (JSON-Array)__: die Event-Customers, welche neu angelegt wurden
    * __event_customer_id (Integer)__: die neue Event-Customer-ID (wird vom System automatisch vergeben)
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

  __2. Updaten bestehender Locations__

__URL__: https://datacenter.predecy.de/predecy-api/predecy/rest/data/setEventCustomers
__Method__: POST  
__Content-Type__: application/json  
__Body (Parameter als JSON-Objekt)__:
* __api_key (String)__: der API-Key zur Authentifizierung und Autorisierung
* __event_customers (JSON-Array)__: die Event-Customers, welche aktualisiert werden sollen
    * __event_customer_id (Integer)__: die Event-Customer-ID
    * **name (String) _optional_**: der Name des Event-Customers
    * **key (String) _optional_**: ein Key zur spezifischen Beschreibung des Event-Customers (z.B. Kundennummer)

  Beispiel:  
  ```
  {
    "api_key": "103504d8-05fd-1ea-9d18-0242d0a8d003",  
    "event_customers": [
        {
            "event_customer_id": 492,
            "name": "Curcuma Solutions AG",  
        }
    ]
  }
  ```
  
__Response__:
* __event_customers (JSON-Array)__: die Event-Customers, welche neu angelegt wurden
    * __event_customer_id (Integer)__: die aktualisierte Event-Customer-ID
    * __name (String)__: der Name des Event-Customers
    * __key (String)__: ein Key zur spezifischen Beschreibung des Event-Customers (z.B. Kundennummer)
  
  Beispiel: 
  ```
  {
      "event_customers": [
          {
            "event_customer_id": 492,
            "event_customer_name": "Curcuma Solutions AG",
            "key": "16543"  
          }
      ]
  }
  ```
  
  [Impressum](https://www.spicetech.de/#Impressum)
  
