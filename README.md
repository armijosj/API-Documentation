# Description
A simple API to access Winnipeg Transit information. User can access information such as time tables, stops in a route and bus stop in an area. 

# List of endpoints
## GET: Timetable/{stop number}
Returns the timetable for the specified stop number. 

## GET: Stops/{area code} or Stops/search?area-code={area code}
Returns a list of bus stops that are inside the specified area code.

## GET: Stops/Route/{route number} or Stops/search?route={route}
Returns all the stops that the specified route goes through.


# JSON

# Sample request with sample response
TimeTimetable/{stop number}
- GET: Timetable/17784
    - Returns: 
    ```
    {
        "results":[
            {
                "routeId": 671,
                "lastStopName": "South Point"
                "time": "11:00:00"
            },
            {
                "StopId": 72,
                "lastStopName": "Richmond"
                "time": "11:15:00"
            },
            {
                "StopId": 51,
                "lastStopName": "Downtown"
                "time": "11:30:00"
            }
        ]
    }
    ```
- GET: Stops/R3T2M9
    - Returns:
    ```
    {
        [
            "12345",
            "67890",
            "72523"
        ]
    }
    ```
- GET: Stops/Route/671
    - Returns:
    ```
    {
        "results":[
            {
                "stopId": 12345,
                "stopName": "Hawkstead"
            },
            {
                "stopId": 67898,
                "stopName": "Richmond"
            },
            {
                "stopId": 54313,
                "stopName": "Thornsdale"
            }
        ]
    }
    ```

