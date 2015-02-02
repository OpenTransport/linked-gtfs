# Linked GTFS

The Linked General Transit Feed Specification (Linked GTFS) is a mapping of the GTFS in CSV reference towards RDF. It stays as close as possible to the CSV reference, including small additions to enhance usability.

See also:
 * The introduction at http://vocab.gtfs.org
 * The [public CSV specification](https://developers.google.com/transit/gtfs/reference) where all semantics are derived from
 * The [spec](spec.md)

### Editors

 * Pieter Colpaert (Open Knowledge | iMinds - Ghent University - MultiMedia Lab)
 * Andrew Byrd (Conveyal)

## Context

The [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/reference) defines an open standard data format for public transport schedules. Unlike other public transport data standards, it emerged to meet specific practical needs in passenger information systems and is a relatively simple tabular format. GTFS first appeared in 2005 through cooperation between a public agency and a private company, as a way for Portland, Oregon's TriMet agency to provide schedule data for the then-experimental Google Transit routing service. The standard is now maintained and revised through a public process on the [gtfs-changes mailing list](https://groups.google.com/forum/#!forum/gtfs-changes). For more information on the origins of GTFS, see [chapter 10 of Beyond Transparency](http://beyondtransparency.org/chapters/part-2/pioneering-open-data-standards-the-gtfs-story/).

An analysis of archived public feeds in the summer of 2012 found that after a period of rapid growth, "about one fourth of the agencies in the U.S. have open route and schedule data, representing about 85 percent of the total passenger-miles served." [[1]](http://blog.openplans.org/2012/07/in-public-transit-the-number-of-passenger-miles-served-by-agencies-with-open-data-has-skyrocketed/) Open transit data is also becoming widely available in Europe. Most of this data is provided in the GTFS format either directly by transport agencies or by third party data aggregators.
