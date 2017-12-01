# Developing an FTC Data Standard
#### Oliver Bates, Sarah Wise and Adrian Friday

## Introduction
In this document we layout a data standard that captures the detail and complexity of the day-to-day efforts of last mile logistics, grounded bu the on-going empirical work of the EPSRC project FTC2050. The data standard looks to provide a standard way of formatting and describing data to enable data analytics and open data relating to last mile freight.

## Scenarios

In this section, we use a series of short scenarios relating to the work undertaken in FTC2050 to help describe why particular data is interesting, and what data is import in the scope of last mile logistics.

**Planning rounds in the last mile.**
The *jobs* (represented by consignments and manifests) are scheduled for delivery. Jobs are often close in geogrpahical *location* (e.g. lat, lon, address) and can be completed on a *round*. A job,

 Rounds are allocated to a *worker* who will complete the *jobs*.
Work/job balancing happens dependant on the number of jobs that day, the *vehicles* available and other required *assests* such as trolleys or backpacks. Vehicles and assests have limited *capacity* (e.g. fully laiden weight, internal dimensions), *range*

**Loading vehicles.** Understand the *order* in which items are loaded into the van helps understand the round order. The *weight*, *size*, and *priority* (e.g. time prioritised) of a parcel or consignment factor into the order in which parcels are loaded into vehicles.

**Navigating through the city.**
***waypoints*** representing walking and driving in the city
***parking location***


***Secondary Data***:

**Navigating inside buildings.** ***waypoint*** data should also capture ***elevation***, and additional information can be made available to help the worker get to the ***deliver location*** within a multi-story, multi-purpose building more effectively


## Requirements

- Extendability
asdas d

## Data Structure and Description
Each

For where we want anonyminty to be a concern we should use GUID () to help mask the original data
### jobs

```javascript
job = {
        id :'0001', //unique id of the job
        round_id: '00001', //id of the round that the job is on
        barcode: '', //barcode number of the item
        consignee:'Adrian Friday Inc', //the client who has placed the order
        customer:'Julian Allen', //the inasdateded customer
        address:'',
        postcode:'',
        geo_coded_address = {
                lat:'',
                lon:''
            },
        priority = 'Next 10 Minutes',
        pick_up_by:'', //the time by which the item should be collected for delivery
        pick_up_time:''
        drop_off_by
}

```

### waypoints

```javascript
waypoint = {
        id :'0001',
        trip_id: '0001'
        lat: '0.43',
        lon: '52.12',
        altitude: ''
}

```


## JSON Schema

```
{ job:
}

```
