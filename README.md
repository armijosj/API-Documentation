# Description
A simple API to access Winnipeg Transit information. User can access information such as timetables, stops in a route, and bus stop in an area. 

# List of endpoints
### GET: Timetable/{stop number}
Returns the timetable for the specified stop number. 

### GET: Stops/search?area-code={area code}
Returns a list of bus stops that are inside the specified area code.

### GET: Route/{route number}
Returns all the stops that the specified route goes through.


# Resources: Formatted as JSON

- The result data is formatted using JSON.
 
*NOTE: All the times are in UTC.*

### GET: Timetable/{stop number}
```
{
   "BusSchedule": [ 
        {
            "routeId": BUS_NUMBER, 
            "lastStopName": FINAL_STOP_NAME, 
            "time": TIME
        }, 
    ...
   ]
}
```

### GET: Stops/search?area-code={area code}
```
{
    "AreaStops":
    {
        "stopId": STOP_CODE,
        "stopName": STOP_NAME,
        "routeIds": [
            STOP_NUM, 
            STOP_NUM, 
            STOP_NUM
            ...
        ]
    }
}
```

### GET: Route/{route}

```
{
    "RouteStops":
    {
        "stopId": STOP_CODE,
        "stopName": STOP_NAME,
        "routeIds": [
            STOP_NUM,
            ...
        ]
    }
}
```

# Sample request with sample response
TimeTimetable/{stop number}
### GET: Timetable/17784
Returns:
```
    {
        "BusSchedule":[
            {
                "routeId": 671,
                "lastStopName": "South Point",
                "time": "11:00:00"
            },
            {
                "routeId": 72,
                "lastStopName": "Richmond",
                "time": "11:15:00"
            },
            {
                "routeId": 51,
                "lastStopName": "Downtown",
                "time": "11:30:00"
            }
        ]
    }
```
### GET: Stops/search?area-code=R3T2M9
Returns:
```
    {
        "AreaStops":[
            {
                "stopId": 12345,
                "stopName": "Hawkstead",
                "routeIds": [
                    51,
                    61,
                    72
                ]
            },
            {
                "stopId": 67898,
                "stopName": "Richmond",
                "routeIds": [
                    91,
                ]
            },
            {
                "stopId": 54313,
                "stopName": "Thornsdale",
                "routeIds": [
                    72,
                    80
                ]
            }
        ]
    }
```
### GET: Route/671
Returns:
```
    {
        "RouteStops":[
            {
                "stopId": 12351,
                "stopName": "Jimbo",
                "routeIds": [
                    671,
                    672
                ]
            },
            {
                "stopId": 46847,
                "stopName": "Wumbo",
                "routeIds": [
                    671
                ]
            },
            {
                "stopId": 35789,
                "stopName": "Gumbo",
                "routeIds": [
                    671
                ]
            }
        ]
    }
```
