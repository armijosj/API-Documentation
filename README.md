# Description
A simple API to access Winnipeg Transit information. User can access information such as timetables, stops in a route, and bus stop in an area. 

# List of endpoints

Using **GET** request.

### GET: /Timetable/{bus-stop num}
Returns the timetable for the specified stop number. 

### GET: /Stops/search?area-code={area code}
Returns a list of bus stops that are inside the specified area code.

### GET: /Route/{route number}
Returns all the stops that the specified route goes through.


# Resources: Formatted as JSON

- The result data is formatted using JSON.
- The URL would be `https://winnipeg-transit.org/json`.
 
*NOTE: All the times are in UTC.*

### GET: /Timetable/{bus-stop num}
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

### GET: /Stops/search?area-code={area code}
```
{
    "AreaStops":
    {
        "stopId": STOP_CODE,
        "stopName": STOP_NAME,
        "routeIds": [
            ROUTE_ID, 
            ROUTE_ID, 
            ROUTE_ID
            ...
        ]
    }
}
```

### GET: /Route/{route id}

```
{
    "RouteStops":
    {
        "stopId": STOP_CODE,
        "stopName": STOP_NAME,
        "routeIds": [
            ROUTE_ID,
            ...
        ]
    }
}
```

# Sample request with sample response
TimeTimetable/{bus-stop num}
### GET: /Timetable/17784
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
### GET: /Stops/search?area-code=R3T2M9
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
### GET: /Route/671
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

## Group members
1. Wen, Chu Hao
2. Armijos, Jun
3. Patel, Khush Bhrugesh
4. Sood, Tanish
