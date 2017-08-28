# Endor

The forest moon, and home of the Ewoks. Endor is the location of the shield 
transmitter for the Death Star. (MK 2)

Endor is the overall project name for the monitoring solution developed by myself.

It consists of three parts:

## Backend

The backend has two pieces to it, the client, to be run on the systems
to be monitored, and the database, which will exist in a centralized location.

###Client

A Golang client to be run on each system being monitored, it will collect 
the following data:
 
 * CPU usage data (Average % usage over all cpus out of 100.)
    * (System %)
    * (User %)
    * (Idle %) 

 * Memory Usage information 
    * (Average total %)

 * Disk usage Information
    * (Free/Used over each disk)

 * Network Usage information
    * Kb up
    * Kb down

 * Number of processes

### Database

A MongoDB backend with basic http authentication, and a REST API, 
also written in Golang.

This mongo instance will hold data in the following format:

```json
{
    id: []string //unique ID
    hostname: string
    timestamps: []string
    metrics: {
        cpu: {
            system: []string, //Percent
            user: []string, //Percent
            idle: []string //Percent
        },
        memory: []string, //usedPercent
        disks: []{
            name: string, //name of disk (mount point/Drive letter)
            used: []string  //percent
            },
        net: {
            up: []string, //Kb up
            down: []string //Kb down
            },
        processes: []string //numProcesses
    }
}
```

##Frontend

In front of all of this, I will have a React front end, using Redux 
as a data store, and ChartsJS for viewing data.

Charts will be designed to overlap based on type for each host. 

e.g. 

A host with the name `galvanize` would show CPU System, User, and Idle
metrics all in one metric with a hover overlay.

Other design decisions will be done as the project progresses, as this is a 
solo project.
