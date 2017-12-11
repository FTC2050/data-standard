## Scenarios

In this section, we use a series of short scenarios relating to the work undertaken in FTC2050 to help describe why particular data is interesting, and what data is import in the scope of last mile logistics.

In these scenarios, important ***objects*** are bold and italic, with *parameters* italicised.

#### Jobs and rounds in the last mile.
The ***jobs*** (represented by consignments and manifests) are scheduled for delivery. A ***worker*** (e.g. driver) is allocated a number of ***jobs*** to complete in a day. The allocation for B2B and B2C consignments (primarily deliveries) typically happens over night, with a small amount of ad hoc collections being allocated during the daily operation.

  **Events** capture the status of **jobs** through the system as they are processed, loaded and completed (or fail).  ***Jobs*** are some times close in geographical location (e.g. latitude, longitude, address) and can be completed on a ***round***, other times jobs are littered across the city and the driver is left to decide on the most optimal round.

A ***job***, represents work where a contract has been agreed by a particular consigner (customer) to a consignee (recipient), consignments are completed by a courier (e.g. logistics/freight company/free lance). Each job will have a series of ***events***. ***Events*** are represented with a *timestamp* and an event *status*.

A round (or ***trip***) represents a series of jobs that a worker completes during the day. Rounds are allocated to a ***worker*** who perform a number of ***jobs*** on their rounds.
Work/job balancing happens dependant on the number of jobs that day, the ***vehicles*** available and other required ***assets***, such as trolleys or backpacks. Vehicles and assets have limited *capacity* (e.g. fully laden weight, internal dimensions), *range* (e.g. the maximum range the vehicle can travel).

#### Loading vehicles
Understanding the *order* in which items are loaded into the van helps understand the round order. The *weight*, *size* (can the parcel(s) fit on the vehicle?), *grouping* (multiple parcels delivered to the same address) and *priority* (e.g. time prioritised) of a parcel or consignment factor into the order in which parcels are loaded into vehicles.

These parameters potentially effect the ordering of a delivery round.

#### Navigating through the city
As **workers** navigate go about their **trips** through the city, completing their allocated  **jobs** using **vehicles** their location in space and time can help understand optimal routes through the city, how to navigate on foot, the relationship between driver effectiveness and congestion, optimal spotting and parking points, and the temporal and spatial overlap of jobs and trips. Driver and vehicle navigation can be represented as a series of geographical **waypoints**.


### Secondary Data

- Looking up location data of the

#### Navigating inside buildings.
Our work has demonstrated how the distance and navigation inside of a building has a hold over the effectiveness of the delivery driver.

To help better utilise internal navigation, *waypoint* data should also capture *elevation*, and additional information can be made available to help the worker get to the *delivery location* within a multi-story, multi-purpose building more effectively
