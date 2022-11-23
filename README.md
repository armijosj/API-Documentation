# Description
A simple API to access Winnipeg Transit information. User can access information such as time tables, stops in a route and bus stop in an area. 

# List of endpoints
- GET: Timetable/{stop number}
    - Description: 
- GET: Stops/{area code}
    - Description"
- GET: Stops/Route/{route number}

# JSON

# Sample request with sample response
TimeTimetable/{stop number}
- GET: Timetable/17784
    - Returns: 
    {
        [
            "671, South Point, 11:00:00",
            "72, Richmond, 11:15:00",
            "51, Downtown, 11:30:00" 
        ]
    }
- GET: Stops/R3T2M9
    - Returns:
    {
        [
            "12345",
            "67890",
            "72523"
        ]
    }
- GET: Stops/Route/671
    - Returns:
    {
        [
            "12345, Hawkstead",
            "67898, Richmond",
            "54313, Thornsdale"
        ]
    }