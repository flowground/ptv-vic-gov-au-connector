# ![LOGO](logo.png) PTV Timetable API - Version 3 **flow**ground Connector

## Description

A generated **flow**ground connector for the PTV Timetable API - Version 3 API (version v3).

Generated from: https://api.apis.guru/v2/specs/ptv.vic.gov.au/v3/swagger.json<br/>
Generated at: 2019-05-07T17:43:46+03:00

## API Description

The PTV Timetable API provides direct access to Public Transport Victoria’s public transport timetable data.

The API returns scheduled timetable, route and stop data for all metropolitan and regional train, tram and bus services in Victoria, including Night Network(Night Train and Night Tram data are included in metropolitan train and tram services data, respectively, whereas Night Bus is a separate route type).

The API also returns real-time data for metropolitan train, tram and bus services (where this data is made available to PTV), as well as disruption information, stop facility information, and access to myki ticket outlet data.

This Swagger is for Version 3 of the PTV Timetable API. By using this documentation you agree to comply with the licence and terms of service.

Train timetable data is updated daily, while the remaining data is updated weekly, taking into account any planned timetable changes (for example, due to holidays or planned disruptions). The PTV timetable API is the same API used by PTV for its apps. To access the most up to date data PTV has (including real-time data) you must use the API dynamically.

You can access the PTV Timetable API through a HTTP or HTTPS interface, as follows:

    base URL / version number / API name / query string
The base URL is either:
  *  http://timetableapi.ptv.vic.gov.au
or
  *  https://timetableapi.ptv.vic.gov.au

The Swagger JSON file is available at http://timetableapi.ptv.vic.gov.au/swagger/docs/v3

Frequently asked questions are available on the PTV website at http://ptv.vic.gov.au/apifaq

Links to the following information are also provided on the PTV website at http://ptv.vic.gov.au/ptv-timetable-api/
* How to register for an API key and calculate a signature
* PTV Timetable API V2 to V3 Migration Guide
* Documentation for Version 2 of the PTV Timetable API
* PTV Timetable API Data Quality Statement

All information about how to use the API is in this documentation. PTV cannot provide technical support for the API.

Credits: This page has been based on Steve Bennett's http://opentransportdata.org/, used with permission.


## Authorization

This API does not require authorization.

## Actions

### View departures for all routes from a stop

*Tags:* `Departures`

#### Input Parameters
* `route_type` - _required_ - Number identifying transport mode; values returned via RouteTypes API
    Possible values: 0, 1, 2, 3, 4.
* `stop_id` - _required_ - Identifier of stop; values returned by Stops API
* `platform_numbers` - _optional_ - Filter by platform number at stop
* `direction_id` - _optional_ - Filter by identifier of direction of travel; values returned by Directions API - /v3/directions/route/{route_id}
* `look_backwards` - _optional_ - Indicates if filtering runs (and their departures) to those that arrive at destination before date_utc (default = false). Requires max_results &gt; 0.
* `gtfs` - _optional_ - Indicates that stop_id parameter will accept "GTFS stop_id" data
* `date_utc` - _optional_ - Filter by the date and time of the request (ISO 8601 UTC format) (default = current date and time)
* `max_results` - _optional_ - Maximum number of results returned
* `include_cancelled` - _optional_ - Indicates if cancelled services (if they exist) are returned (default = false) - metropolitan train only
* `expand` - _optional_ - List objects to be returned in full (i.e. expanded) - options include: all, stop, route, run, direction, disruption
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View departures for a specific route from a stop

*Tags:* `Departures`

#### Input Parameters
* `route_type` - _required_ - Number identifying transport mode; values returned via RouteTypes API
    Possible values: 0, 1, 2, 3, 4.
* `stop_id` - _required_ - Identifier of stop; values returned by Stops API
* `route_id` - _required_ - Identifier of route; values returned by Routes API - v3/routes
* `direction_id` - _optional_ - Filter by identifier of direction of travel; values returned by Directions API - /v3/directions/route/{route_id}
* `look_backwards` - _optional_ - Indicates if filtering runs (and their departures) to those that arrive at destination before date_utc (default = false). Requires max_results &gt; 0.
* `gtfs` - _optional_ - Indicates that stop_id parameter will accept "GTFS stop_id" data
* `date_utc` - _optional_ - Filter by the date and time of the request (ISO 8601 UTC format) (default = current date and time)
* `max_results` - _optional_ - Maximum number of results returned
* `include_cancelled` - _optional_ - Indicates if cancelled services (if they exist) are returned (default = false) - metropolitan train only
* `expand` - _optional_ - List objects to be returned in full (i.e. expanded) - options include: all, stop, route, run, direction, disruption
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View directions that a route travels in

*Tags:* `Directions`

#### Input Parameters
* `route_id` - _required_ - Identifier of route; values returned by Routes API - v3/routes
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all routes for a direction of travel

*Tags:* `Directions`

#### Input Parameters
* `direction_id` - _required_ - Identifier of direction of travel; values returned by Directions API - /v3/directions/route/{route_id}
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all routes of a particular type for a direction of travel

*Tags:* `Directions`

#### Input Parameters
* `direction_id` - _required_ - Identifier of direction of travel; values returned by Directions API - /v3/directions/route/{route_id}
* `route_type` - _required_ - Number identifying transport mode; values returned via RouteTypes API
    Possible values: 0, 1, 2, 3, 4.
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all disruptions for all route types

*Tags:* `Disruptions`

#### Input Parameters
* `route_types` - _optional_ - Filter by route_type; values returned via RouteTypes API
* `disruption_modes` - _optional_ - Filter by disruption_mode; values returned via v3/disruptions/modes API
* `disruption_status` - _optional_ - Filter by status of disruption
    Possible values: current, planned.
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### Get all disruption modes

*Tags:* `Disruptions`

#### Input Parameters
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all disruptions for a particular route

*Tags:* `Disruptions`

#### Input Parameters
* `route_id` - _required_ - Identifier of route; values returned by Routes API - v3/routes
* `disruption_status` - _optional_ - Filter by status of disruption
    Possible values: current, planned.
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all disruptions for a particular route and stop

*Tags:* `Disruptions`

#### Input Parameters
* `route_id` - _required_ - Identifier of route; values returned by Routes API - v3/routes
* `stop_id` - _required_ - Identifier of stop; values returned by Stops API - v3/stops
* `disruption_status` - _optional_ - Filter by status of disruption
    Possible values: current, planned.
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all disruptions for a particular stop

*Tags:* `Disruptions`

#### Input Parameters
* `stop_id` - _required_ - Identifier of stop; values returned by Stops API - v3/stops
* `disruption_status` - _optional_ - Filter by status of disruption
    Possible values: current, planned.
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View a specific disruption

*Tags:* `Disruptions`

#### Input Parameters
* `disruption_id` - _required_ - Identifier of disruption; values returned by Disruptions API - /v3/disruptions OR /v3/disruptions/route/{route_id}
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### List all ticket outlets

*Tags:* `Outlets`

#### Input Parameters
* `max_results` - _optional_ - Maximum number of results returned (default = 30)
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### List ticket outlets near a specific location

*Tags:* `Outlets`

#### Input Parameters
* `latitude` - _required_ - Geographic coordinate of latitude
* `longitude` - _required_ - Geographic coordinate of longitude
* `max_distance` - _optional_ - Filter by maximum distance (in metres) from location specified via latitude and longitude parameters (default = 300)
* `max_results` - _optional_ - Maximum number of results returned (default = 30)
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View the stopping pattern for a specific trip/service run

*Tags:* `Patterns`

#### Input Parameters
* `run_id` - _required_ - Identifier of a trip/service run; values returned by Runs API - /v3/route/{route_id} and Departures API
* `route_type` - _required_ - Number identifying transport mode; values returned via RouteTypes API
    Possible values: 0, 1, 2, 3, 4.
* `expand` - _required_ - Objects to be returned in full (i.e. expanded) - options include: all, stop, route, run, direction, disruption. By default disruptions are expanded.
* `stop_id` - _optional_ - Filter by stop_id; values returned by Stops API
* `date_utc` - _optional_ - Filter by the date and time of the request (ISO 8601 UTC format)
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all route types and their names

*Tags:* `RouteTypes`

#### Input Parameters
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View route names and numbers for all routes

*Tags:* `Routes`

#### Input Parameters
* `route_types` - _optional_ - Filter by route_type; values returned via RouteTypes API
* `route_name` - _optional_ - Filter by name  of route (accepts partial route name matches)
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View route name and number for specific route ID

*Tags:* `Routes`

#### Input Parameters
* `route_id` - _required_ - Identifier of route; values returned by Departures, Directions and Disruptions APIs
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all trip/service runs for a specific route ID

*Tags:* `Runs`

#### Input Parameters
* `route_id` - _required_ - Identifier of route; values returned by Routes API - v3/routes.
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all trip/service runs for a specific route ID and route type

*Tags:* `Runs`

#### Input Parameters
* `route_id` - _required_ - Identifier of route; values returned by Routes API - v3/routes.
* `route_type` - _required_ - Number identifying transport mode; values returned via RouteTypes API
    Possible values: 0, 1, 2, 3, 4.
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all trip/service runs for a specific run ID

*Tags:* `Runs`

#### Input Parameters
* `run_id` - _required_ - Identifier of a trip/service run; values returned by Runs API - /v3/route/{route_id} and Departures API
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View the trip/service run for a specific run ID and route type

*Tags:* `Runs`

#### Input Parameters
* `run_id` - _required_ - Identifier of a trip/service run; values returned by Runs API - /v3/route/{route_id} and Departures API
* `route_type` - _required_ - Number identifying transport mode; values returned via RouteTypes API
    Possible values: 0, 1, 2, 3, 4.
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View stops, routes and myki ticket outlets that match the search term

*Tags:* `Search`

#### Input Parameters
* `search_term` - _required_ - Search text (note: if search text is numeric and/or less than 3 characters, the API will only return routes)
* `route_types` - _optional_ - Filter by route_type; values returned via RouteTypes API (note: stops and routes are ordered by route_types specified)
* `latitude` - _optional_ - Filter by geographic coordinate of latitude
* `longitude` - _optional_ - Filter by geographic coordinate of longitude
* `max_distance` - _optional_ - Filter by maximum distance (in metres) from location specified via latitude and longitude parameters
* `include_addresses` - _optional_ - Placeholder for future development; currently unavailable
* `include_outlets` - _optional_ - Indicates if outlets will be returned in response (default = true)
* `match_stop_by_suburb` - _optional_ - Indicates whether to find stops by suburbs in the search term (default = true)
* `match_route_by_suburb` - _optional_ - Indicates whether to find routes by suburbs in the search term (default = true)
* `match_stop_by_gtfs_stop_id` - _optional_ - Indicates whether to search for stops according to a metlink stop ID (default = false)
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all stops near a specific location

*Tags:* `Stops`

#### Input Parameters
* `latitude` - _required_ - Geographic coordinate of latitude
* `longitude` - _required_ - Geographic coordinate of longitude
* `route_types` - _optional_ - Filter by route_type; values returned via RouteTypes API
* `max_results` - _optional_ - Maximum number of results returned (default = 30)
* `max_distance` - _optional_ - Filter by maximum distance (in metres) from location specified via latitude and longitude parameters (default = 300)
* `stop_disruptions` - _optional_ - Indicates if stop disruption information will be returned (default = false)
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View all stops on a specific route

*Tags:* `Stops`

#### Input Parameters
* `route_id` - _required_ - Identifier of route; values returned by Routes API - v3/routes
* `route_type` - _required_ - Number identifying transport mode; values returned via RouteTypes API
    Possible values: 0, 1, 2, 3, 4.
* `direction_id` - _optional_ - An optional direction; values returned by Directions API. When this is set, stop sequence information is returned in the response.
* `stop_disruptions` - _optional_ - Indicates if stop disruption information will be returned (default = false)
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

### View facilities at a specific stop (Metro and V/Line stations only)

*Tags:* `Stops`

#### Input Parameters
* `stop_id` - _required_ - Identifier of stop; values returned by Stops API
* `route_type` - _required_ - Number identifying transport mode; values returned via RouteTypes API
    Possible values: 0, 1, 2, 3, 4.
* `stop_location` - _optional_ - Indicates if stop location information will be returned (default = false)
* `stop_amenities` - _optional_ - Indicates if stop amenity information will be returned (default = false)
* `stop_accessibility` - _optional_ - Indicates if stop accessibility information will be returned (default = false)
* `stop_contact` - _optional_ - Placeholder for future development; currently unavailable
* `stop_ticket` - _optional_ - Placeholder for future development; currently unavailable
* `gtfs` - _optional_ - Incdicates whether the stop_id is a GTFS ID or not
* `stop_staffing` - _optional_ - Indicates if stop staffing information will be returned (default = false)
* `stop_disruptions` - _optional_ - Indicates if stop disruption information will be returned (default = false)
* `token` - _optional_ - Please ignore
* `devid` - _optional_ - Your developer id
* `signature` - _optional_ - Authentication signature for request

## License

**flow**ground :- Telekom iPaaS / ptv-vic-gov-au-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
