# couchbase-event-sdk
The Couchbase Event SDK is a Client Server Framework that gets Deployed and acts as a event stream driven couchbase client that supports pub/sub so it turns Couchbase into a Distributed Messaging Quque and Log Stream Processing System and so saves you a lot of extra Infrastructure to Maintain!

## Features
- Autoscaling 
- serverless Ready
- supports Firebase like pub/sub streams
- Designed to Handle Millions of Subscribtions and Publishes
- Replacement for Kafka and Storm or similar Stream Processors + RDB

## Goal
Today many Companys have the Need to run and Manage diffrent Infrastructural Parts we from Direktspeed are working on Replace all that with a Uniqe Platfrom based on Couchbase and allow Step by Step and even Partial Migration to that total new Mind Blowing Concepts.


## Example

```js
// The Server Part
const eventStream = require('couchbase-event-sdk');
eventStream.connect('couchbase://127.0.0.1',...RBAC)


// Example Client
/** You can Subscribe to the data in 2 modes: key or value
  * key === returns only key and event type to allow custom querys to fetch only importent parts
  * value === returns key: value pair 
  */
const listenForChangesOnKeys = eventStream
  .subscribe('key**supports glob and wildcard**','val.deep.name', 'key') 
  
listenForChangesOnKeys
  .on('update',key=>console.log(`The ${key} got just updated`))
```

Its only a Minimal Example i could write whole books about patterns for that.


This is currently work in Progress by Frank Lemanschik feel free to contact him if you want to support the Development or give him some Money he is Always open for Good Oportunitys. 


## Mock
We have added Mock Servers to make it more easy to Code without the need of a Full Deployed Couchbase + couchbase-event-sdk Cluster.

They mimic the behavior of a Real Couchbase Cluster via couchnode's mock server + some additional extension to simulate the event-streams.
