# Developing an Last Mile Logistics Data Standard
#### Oliver Bates, Sarah Wise and Adrian Friday

## Introduction
In this document we layout a data standard that captures the detail and complexity of the day-to-day efforts of last mile logistics, grounded but the on-going empirical work of the EPSRC project FTC2050. The data standard looks to provide a standard way of formatting and describing data to enable data analytics and open data relating to last mile freight.

## Scenarios

In this section, we use a series of short scenarios relating to the work undertaken in FTC2050 to help describe why particular data is interesting, and what data is import in the scope of last mile logistics.

#### Jobs and rounds in the last mile.
The ***jobs*** (represented by consignments and manifests) are scheduled for delivery. A ***worker*** (e.g. driver) is allocated a number of ***jobs*** to complete in a day. The allocation for B2B and B2C consignments (primarily deliveries) typically happens over night, with a small amount of ad hoc collections being allocated during the daily operation. ***Jobs*** are some times close in geographical location (e.g. lat, lon, address) and can be completed on a ***round***, other times jobs are littered across the city and the driver is left to decide on the most optimal round.
A ***job***, represents work where a contract has been agreed by a particular consigner (customer) to a consignee (recipient), consignments are completed by a courier (e.g. logistics/freight company/free lance). A ***round*** represents a series of jobs that

Rounds are allocated to a ***worker*** who perform a number of ***jobs*** on their rounds.
Work/job balancing happens dependant on the number of jobs that day, the ***vehicles*** available and other required ***assets*** such as trolleys or backpacks. Vehicles and assets have limited ***capacity*** (e.g. fully laden weight, internal dimensions), ***range***

#### Loading vehicles
Understanding the ***order*** in which items are loaded into the van helps understand the round order. The ***weight***, ***size*** (can the parcel(s) fit on the vehicle?), ***grouping*** (multiple parcels delivered to the same address) and ***priority*** (e.g. time prioritised) of a parcel or consignment factor into the order in which parcels are loaded into vehicles.  These parameters potential effect the ordering of a delivery round

#### Navigating through the city

*waypoints* representing walking and driving in the city
*parking location*


### Secondary Data

#### Navigating inside buildings.
Our work has demonstrated how the distance and navigation inside of a building has a hold over the effectiveness of the delivery driver.

To help better utilise internal navigation, ***waypoint*** data should also capture ***elevation***, and additional information can be made available to help the worker get to the ***delivery location*** within a multi-story, multi-purpose building more effectively


## Requirements

- Extendability

## Challenges

- Analysing and visualising large volumes of data
- Choosing the appropriate database technology
- Erroneous data, data handling, data cleansing


## Data Structure and Description

For where we want anonymity to be a concern we should use GUID () to help mask the original data
### jobs

```javascript
job = {
        id :'0001', //unique id of the job
        round_id: '00001', //id of the round that the job is on
        created: '', //the data/time that the job was created - helps contextualise priority, pick up, etc
        parcel_id: '', //barcode number of the item, what if there are multiple parcels?
        consigner:'Adrian Friday Inc', //the client who has placed the order
        consignee:'Julian Allen', //the customer
        address:'31 Fleet Street, London',
        postcode:'EC4Y 1AA',
        geo_coded_address : {
                lat:'51.513853',
                lon:'-0.110101'
            },
        priority : '', //lists the priority of the item, e.g. next day
        pick_up_by:'', //the time by which the item should be collected for delivery
        puck_up_address:'',
        pick_up_time:''
        drop_off_by
}

```
mandatory fields:
- id
- parcel_id
- consigner
- consignee
- address
- postcode

optional fields:

questions:
- what if there are multiple parcels on a job?
- should we be using terms and colloquialism specific to the industry, or should we use more plan and accessible English?

### workers

```javascript
worker = {
        id :'0001',
        name:'Tom Cherrett',
        roles = {'van_driver','loader'}, //the worker may have multiple potential roles that they can work in within last mile logistics
        vehicle_access: {'PERSONAL:001','FLEET:001'}, //
        vehicle_license:{'LGV'},//is preference a thing?
        constraints: {'Bad on Mondays', 'LGV license', 'prefers LGV', 'hates bicycles'},
        tenure: '4 Years',
        employment:{'FTC Logistics','self employed'}

}

```

We should consider look up tables to describe a discrete list of possible:
- *constraints*
- *roles*
- *vehicle_license*
- *vehicle_access* - list of known vehicles that are accessible to workers

### waypoints

```javascript
waypoint = {
        id :'0001',
        trip_id: '0001'
        latitude: '0.43',
        longitude: '52.12',
        elevation: '324.3' // or altitude
}

```
considerations:
- not every GPS device will capture altitude, so might need to be classed as optional
- standard units for elevation/altitude - looks like a [complex discussion](https://gis.stackexchange.com/questions/75572/how-is-elevation-and-altitude-measured)

## JSON Schema

see [JSON Schema folder](/schema)

Contains:
- [job](/schema/ftc_job_schema.json)
-

```
{ job:
}

```
