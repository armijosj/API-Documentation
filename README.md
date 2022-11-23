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
