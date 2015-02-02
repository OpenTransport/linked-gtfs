# Linked GTFS specification

| namespace prefix | URI |
|----:|:----|
| gtfs: |`http://vocab.gtfs.org/terms#` |
| dct:| `http://purl.org/dc/terms/` |
| dcat:| `http://www.w3.org/ns/dcat#`|
| xsd:| `http://www.w3.org/2001/XMLSchema#`|
| rdfs:| `http://www.w3.org/2000/01/rdf-schema#`|
| foaf:| `http://xmlns.com/foaf/0.1/`|
| schema:| `http://schema.org/`|

### [gtfs:Feed](http://vocab.gtfs.org/terms#Feed)

An instance of a [gtfs:Feed](http://vocab.gtfs.org/terms#Feed) is a linked GTFS feed that complies to this specification. The mandatory and recommended properties are there to provide meta-data to the feed.

When something is of a type [gtfs:Feed](http://vocab.gtfs.org/terms#Feed), it
 * is automatically a [dcat:Dataset](http://www.w3.org/ns/dcat#Dataset).
 * has a theme [Transport](http://eurovoc.europa.eu/2015) from the eurovoc taxonomy

_Recommended properties_:
 * [dct:title](http://purl.org/dc/terms/title) - Give a short title to the feed
 * [dct:issued](http://purl.org/dc/terms/issued) (xsd:date) - when was it issued
 * [dct:modified](http://purl.org/dc/terms/modified) (xsd:date) - when was it modified
 * [dcat:contactPoint](http://www.w3.org/ns/dcat#contactPoint) - who to contact in case of an error
 * [dct:temporal](http://purl.org/dc/terms/temporal) - what timespan does it apply to
 * [dct:spatial](http://purl.org/dc/terms/spatial) - what region does it apply to. E.g., <http://www.geonames.org/6695072>
 * [dct:publisher](http://purl.org/dc/terms/publisher) - a link to the data publisher
 * [dct:accrualPeriodicity](http://purl.org/dc/terms/accrualPeriodicity) - how fast does the data change
 * [dct:language](http://purl.org/dc/terms/language) - the main language used by the feed
 * [dcat:distribution](http://www.w3.org/ns/dcat#distribution) - e.g., link to the zip or link to the Linked Data interface
 * [schema:version](http://schema.org/version) - the version number

### [gtfs:Agency](http://vocab.gtfs.org/terms#Agency)

A [gtfs:Agency](http://vocab.gtfs.org/terms#Agency) operates a certain schedule based transport mode.

_Mandatory properties_:
 * [foaf:name](http://xmlns.com/foaf/0.1/name) - a name for the agency
 * [foaf:page](http://xmlns.com/foaf/0.1/page) - a webpage for the agency
 * [gtfs:timeZone](http://vocab.gtfs.org/terms#timeZone) - a timezone as a string (e.g., Europe/Brussels or America/Los_Angeles)

_Recommended properties_:
 * [dct:language](http://purl.org/dc/terms/language) - the main language of the agency
 * [foaf:phone](http://xmlns.com/foaf/0.1/phone) - a single voice telephone number for the specified agency
 * [gtfs:fareUrl](http://vocab.gtfs.org/terms#fareUrl) - the URL of a web page that allows a rider to purchase tickets or other fare instruments for that agency online.

### [gtfs:Stop](http://vocab.gtfs.org/terms#Stop)

A [gtfs:Stop](http://vocab.gtfs.org/terms#Stop) is a physical location where a vehicle stops or leaves. Multiple routes may use the same stop.

_Mandatory properties_:
 * [foaf:name](http://xmlns.com/foaf/0.1/name) - The name of the stop
 * [geo:long](http://www.w3.org/2003/01/geo/wgs84_pos#long), [geo:lat](http://www.w3.org/2003/01/geo/wgs84_pos#lat) - longitude an latitude in WGS84


_Optional properties_:
 * [dct:identifier](http://purl.org/dc/terms/identifier) - a "code": short text or a number that uniquely identifies the stop for passengers. They are often used in phone-based transit information systems or printed on stop signage to make it easier for riders to get a stop schedule or real-time arrival information for a particular stop.
 * [dct:description](http://purl.org/dc/terms/description) - quality information (sic) describing a stop
 * [gtfs:zone](http://vocab.gtfs.org/terms#zone) - defines the fare zone. Zones are required if you want to provide fare information using a [gtfs:FareClass](http://vocab.gtfs.org/terms#FareClass).
 * [foaf:page](http://xmlns.com/foaf/0.1/page) - a page of the stop with more information
 * [gtfs:timeZone](http://vocab.gtfs.org/terms#timeZone) - timezone the stop is in (if different from the [gtfs:Agency](http://vocab.gtfs.org/terms#Agency))
 * [gtfs:parentStation](http://vocab.gtfs.org/terms#parentStation) - If this stop is part of a station, add a link to the station
 * [gtfs:wheelchairAccessible](http://vocab.gtfs.org/terms#wheelchairAccessible) - a wheelchair accessibility type

### [gtfs:Station](http://vocab.gtfs.org/terms#Station)

A [gtfs:Station](http://vocab.gtfs.org/terms#Station) contains 1 or more instances of [gtfs:Stop](http://vocab.gtfs.org/terms#Stop).

_Mandatory properties_:
 * [foaf:name](http://xmlns.com/foaf/0.1/name) - The name of the station
 * [geo:long](http://www.w3.org/2003/01/geo/wgs84_pos#long), [geo:lat](http://www.w3.org/2003/01/geo/wgs84_pos#lat) - longitude an latitude in WGS84

_Optional properties_:
 * [dct:identifier](http://purl.org/dc/terms/identifier) - a "code": short text or a number that uniquely identifies the stop for passengers. They are often used in phone-based transit information systems or printed on stop signage to make it easier for riders to get a stop schedule or real-time arrival information for a particular station.
 * [dct:description](http://purl.org/dc/terms/description) - quality information (sic) describing a station
 * [foaf:page](http://xmlns.com/foaf/0.1/page) - a page of the station with more information
 * [gtfs:timeZone](http://vocab.gtfs.org/terms#timeZone) - timezone the stop is in (if different from the [gtfs:Agency](http://vocab.gtfs.org/terms#Agency))
 * [gtfs:wheelchairAccessible](http://vocab.gtfs.org/terms#wheelchairAccessible) - a wheelchair accessibility type

### Wheelchair accessibility

3 URIs are defined:
 * [gtfs:WheelchairBoardingStatus](http://vocab.gtfs.org/terms#WheelchairBoardingStatus) - a type for accessibility statuses
 * [gtfs:WheelchairAccessible](http://vocab.gtfs.org/terms#WheelchairAccessible)
 * [gtfs:NotWheelchairAccessible](http://vocab.gtfs.org/terms#NotWheelchairAccessible)

### [gtfs:Route](http://vocab.gtfs.org/terms#Route)

A [gtfs:Route](http://vocab.gtfs.org/terms#Route) is a collection of trips which forms a patch a transit vehicle follows.

_Mandatory properties_:
 * [gtfs:shortName](http://vocab.gtfs.org/terms#shortName) - The route_short_name contains the short name of a route. This will often be a short, abstract identifier like "32", "100X", or "Green" that riders use to identify a route, but which doesn't give any indication of what places the route serves. At least one of route_short_name or route_long_name must be specified, or potentially both if appropriate. If the route does not have a short name, please specify a route_long_name and use an empty string as the value for this field.
 * [gtfs:longName](http://vocab.gtfs.org/terms#longName) - The route_long_name contains the full name of a route. This name is generally more descriptive than the route_short_name and will often include the route's destination or stop. At least one of route_short_name or route_long_name must be specified, or potentially both if appropriate. If the route does not have a long name, please specify a route_short_name and use an empty string as the value for this field.
 * [gtfs:routeType](http://vocab.gtfs.org/terms#routeType) - Links to a certain gtfs:RouteType
 * [gtfs:agency](http://vocab.gtfs.org/terms#agency) - Links to an agency (note that this wasn't mandatory in the GTFS CSV spec)

_Optional properties_:
 * [dct:description](http://purl.org/dc/terms/description) - The route_desc field contains a description of a route. Please provide useful, quality information. Do not simply duplicate the name of the route. For example, "A trains operate between Inwood-207 St, Manhattan and Far Rockaway-Mott Avenue, Queens at all times. Also from about 6AM until about midnight, additional A trains operate between Inwood-207 St and Lefferts Boulevard (trains typically alternate between Lefferts Blvd and Far Rockaway)."
 * [gtfs:routeUrl](http://vocab.gtfs.org/terms#routeUrl) - The route_url field contains the URL of a web page about that particular route. This should be different from the agency_url.
 * route:color - In systems that have colors assigned to routes, the route:color field defines a color that corresponds to a route. The color must be provided as a six-character hexadecimal number, for example, 00FFFF. If no color is specified, the default route:color is white (FFFFFF).
 * route:textColor - The textColor property can be used to specify a legible color to use for text drawn against a background of route_color. The color must be provided as a six-character hexadecimal number, for example, FFD700. If no color is specified, the default text color is black (000000).

### gtfs:RouteType

[gtfs:RouteType](http://vocab.gtfs.org/terms#RouteType) is a class to describe the type of transportation used on a route.

Currently, 8 route types are available:
 1. [gtfs:LightRail](http://vocab.gtfs.org/terms#LightRail) - Tram, Streetcar, Light rail. Any light rail or street level system within a metropolitan area.
 2. [gtfs:Subway](http://vocab.gtfs.org/terms#Subway) - Subway, Metro. Any underground rail system within a metropolitan area.
 3. [gtfs:Rail](http://vocab.gtfs.org/terms#Rail) - Rail. Used for intercity or long-distance travel.
 4. [gtfs:Bus](http://vocab.gtfs.org/terms#Bus) - Bus. Used for short- and long-distance bus routes.
 5. [gtfs:Ferry](http://vocab.gtfs.org/terms#Ferry) - Ferry. Used for short- and long-distance boat service.
 6. [gtfs:CableCar](http://vocab.gtfs.org/terms#CableCar) - Cable car. Used for street-level cable cars where the cable runs beneath the car.
 7. [gtfs:Gondola](http://vocab.gtfs.org/terms#Gondola) - Gondola, Suspended cable car. Typically used for aerial cable cars where the car is suspended from the cable.
 8. [gtfs:Funicular](http://vocab.gtfs.org/terms#Funicular) - Funicular. Any rail system designed for steep inclines.

### gtfs:Trip

A collection of [gtfs:StopTimes](http://vocab.gtfs.org/terms#StopTimes) followed by a transit vehicle.

_Mandatory properties_:
 * [gtfs:route](http://vocab.gtfs.org/terms#route) - the trip follows a certain route
 * [gtfs:service](http://vocab.gtfs.org/terms#service) - follows this [gtfs:Service](http://vocab.gtfs.org/terms#Service) for when the trip operates

_Optional properties_:
 * [gtfs:headsign](http://vocab.gtfs.org/terms#headsign) - The trip_headsign field contains the text that appears on a sign that identifies the trip's destination to passengers. Use this field to distinguish between different patterns of service in the same route. If the headsign changes during a trip, you can override the trip_headsign by specifying values for the the stop_headsign field in stop_times.txt.
 * [gtfs:shortName](http://vocab.gtfs.org/terms#shortName) - The trip_short_name field contains the text that appears in schedules and sign boards to identify the trip to passengers, for example, to identify train numbers for commuter rail trips. If riders do not commonly rely on trip names, please leave this field blank. A trip_short_name value, if provided, should uniquely identify a trip within a service day; it should not be used for destination names or limited/express designations.
 * [gtfs:direction](http://vocab.gtfs.org/terms#direction) - binary value that indicates the direction of travel for a trip. Use this field to distinguish between bi-directional trips with the same route. (xsd:boolean)
 * [gtfs:block](http://vocab.gtfs.org/terms#block) - identifies the block to which the trip belongs. A block consists of two or more sequential trips made using the same vehicle, where a passenger can transfer from one trip to the next just by staying in the vehicle
 * [gtfs:shape](http://vocab.gtfs.org/terms#shape) - a link to a shape
 * [gtfs:wheelchairAccessible](http://vocab.gtfs.org/terms#wheelchairAccessible) - whether the trip can be accessed by 1 or more wheelchairs.
 * [gtfs:bikesAllowed](http://vocab.gtfs.org/terms#bikesAllowed) - bikes allowed or not (xsd:boolean)

### gtfs:StopTime

_Mandatory properties_:

 * [gtfs:Trip](http://vocab.gtfs.org/terms#Trip) - link to a trip it is part of
 * [gtfs:arrivalTime](http://vocab.gtfs.org/terms#arrivalTime) - arrival time given as a time calculated starting at noon minus 12h in this format "hh:mm"
 * [gtfs:departureTime](http://vocab.gtfs.org/terms#departureTime) - departure time given as a time calculated starting at noon minus 12h in this format "hh:mm"
 * [gtfs:stop](http://vocab.gtfs.org/terms#stop) - stop
 * [gtfs:stopSequence](http://vocab.gtfs.org/terms#stopSequence) - The [gtfs:stopSequence](http://vocab.gtfs.org/terms#stopSequence) property identifies the order of the stops for a particular trip. The values must increase along the [gtfs:Trip](http://vocab.gtfs.org/terms#Trip) referenced in the [gtfs:trip](http://vocab.gtfs.org/terms#trip) property.

_Optional properties_:
 * [gtfs:headsign](http://vocab.gtfs.org/terms#headsign) - override gtfs:trip's headsign
 * [gtfs:pickupType](http://vocab.gtfs.org/terms#pickupType) - how to get on a transit vehicle at a certain time & location
 * [gtfs:dropOffType](http://vocab.gtfs.org/terms#dropOffType) - how to get off a transit vehicle at a certain time & location
 * [gtfs:distanceTraveled](http://vocab.gtfs.org/terms#distanceTraveled) - Positions a stop as a distance from the first shape point. It represents a real distance traveled along the route in units such as feet or kilometers. This information allows the trip planner to determine how much of the shape to draw when showing part of a trip on the map. The values used for gtfs:distanceTraveled must increase along with gtfs:stopSequence: they cannot be used to show reverse travel along a route.

### [gtfs:PickupType](http://vocab.gtfs.org/terms#PickupType) and [gtfs:DropOffType](http://vocab.gtfs.org/terms#DropOffType)

4 types are defined which are both a [gtfs:PickupType](http://vocab.gtfs.org/terms#PickupType) and a gtfs:DropOffType
 * gtfs:Regular
 * gtfs:NotAvailable
 * gtfs:MustPhone
 * gtfs:MustCoordinateWithDriver

### gtfs:Service

A [gtfs:Service](http://vocab.gtfs.org/terms#Service) identifies a set of dates when a service is available for one or more routes

_Mandatory properties_:
 * [gtfs:serviceRule](http://vocab.gtfs.org/terms#serviceRule) - links to a certain gtfs:ServiceRule

### gtfs:ServiceRule, [gtfs:CalendarRule](http://vocab.gtfs.org/terms#CalendarRule) and gtfs:CalendarDateRule

#### gtfs:CalendarRule

_Mandatory properties_:
 * gtfs:monday, gtfs:tuesday, gtfs:wednesday, gtfs:thursday, gtfs:friday, gtfs:saturday, [gtfs:sunday](http://vocab.gtfs.org/terms#sunday) - booleans whether on
 * [dct:temportal](http://purl.org/dc/terms/temportal) - time period in which a startDate and an endDate are given (e.g., using [schema:startDate](http://schema.org/startDate) and schema:endDate)

#### gtfs:CalendarDateRule

_Mandatory properties_:
 * [dct:date](http://purl.org/dc/terms/date) - the date the CalendarDateRule applies
 * [gtfs:dateAddition](http://vocab.gtfs.org/terms#dateAddition) - A boolean whether to add (true) or remove (false) a date

### gtfs:FareClass

A fare class defines a class of pricing. It's a subclass of [schema:PriceSpecification](https://schema.org/PriceSpecification) and extends it with transit specific properties.

_Mandatory properties_
 * schema:price
 * schema:priceCurrency
 * gtfs:paymentMethod: is gtfs:OnBoard or gtfs:BeforeBoarding
 * gtfs:transfers - one of these: gtfs:NoTransfersAllowed, gtfs:OneTransfersAllowed, gtfs:TwoTransfersAllowed, gtfs:UnlimitedTransfersAllowed
_Optional properties_
 * gtfs:transferExpiryTime - time until a transfer expires (in seconds)

### gtfs:FareRule

A rule which binds a gtfs:FareClass to a part of the network.

_Mandatory properties_
* gtfs:fareClass - links to one gtfs:FareClass

_Optional properties (yet mandatory to use at least 1)_
 * gtfs:route - the fare class is applicable to this route
 * gtfs:originZone - the fare class is applicable to this originZone
 * gtfs:destinationZone - An optional destinationZone can be given as well
 * gtfs:zone - is applicable only within this gtfs:Zone

### gtfs:Zone

A class to describe a zone

_Optional properties_
 * rdfs:label - a label to give to the specific zone

### gtfs:Shape

> Discussion: wouldn't it be better to reuse GML?

A shape exists out of different gtfs:ShapePoints.

_Mandatory properties_:
 * [gtfs:shapePoint](http://vocab.gtfs.org/terms#shapePoint) - links more than  1 [gtfs:ShapePoint](http://vocab.gtfs.org/terms#ShapePoint)s to a Shape.

### gtfs:ShapePoint

_Mandatory properties_:
 * [geo:long](http://www.w3.org/2003/01/geo/wgs84_pos#long), [geo:lat](http://www.w3.org/2003/01/geo/wgs84_pos#lat) - longitude an latitude in WGS84
 * [gtfs:pointSequence](http://vocab.gtfs.org/terms#pointSequence) - The gtfs:pointSequence field associates the latitude and longitude of a shape point with its sequence order along the shape. The values must increase along the trip.

_Optional properties_:
 * [gtfs:distanceTraveled](http://vocab.gtfs.org/terms#distanceTraveled) - positions a gtfs:shapepoint as a distance traveled along a shape from the first gtfs:ShapePoint.

### gtfs:Frequency

Describes a frequency of a stop instead of absolute stop times. If a certain gtfs:StopTime is defined, then these stoptimes define the sequence and the time difference between each stop.

_Mandatory properties_
 * gtfs:trip - links to the trip which it applies to
 * gtfs:startTime - specifies the time at which service begins with the specified frequency.
 * gtfs:endTime - indicates the time at which service changes to a different frequency (or ceases) at the first stop in the trip.
 * gtfs:headwaySeconds - indicates the time between departures from the same stop (headway) for this trip type, during the time interval specified by start_time and end_time.
 * gtfs:exactTimes: false: Frequency-based trips are not exactly scheduled. true: Frequency-based trips are exactly scheduled.

### gtfs:TransferRule

Define additional rules for making connections between routes.

_Mandatory properties_:
 * gtfs:originStop & gtfs:destinationStop: indicate the this transfer rule applies only when going from this origin to this destination.
 * gtfs:transferType: links to a gtfs:TransferType, when can be: gtfs:RecommendedTransfer, gtfs:EnsuredTransfer, gtfs:MinimumTimeTransfer, or gtfs:NoTransfer
 * gtfs:minimumTransferTime: a non negative number in seconds: This transfer requires a minimum amount of time between arrival and departure to ensure a connection. The time required to transfer is specified by gtfs:minimumTransferTime.
