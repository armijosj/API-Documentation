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
        [
            "671, South Point, 11:00:00",
            "72, Richmond, 11:15:00",
            "51, Downtown, 11:30:00" 
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
        [
            "12345, Hawkstead",
            "67898, Richmond",
            "54313, Thornsdale"
        ]
    }
    ```

