!SLIDE center

![Riak Logo](riak-logo.png)

# Riak in Production #
## Stories from the Trenches #

!SLIDE bullets

# `self()` #

* Mathias Meyer
* [@roidrage](http://twitter.com/roidrage)

!SLIDE

# What is Riak? #

!SLIDE

## Scalable Data Store ##

!SLIDE

## No Master Nodes ##

!SLIDE

## Fault-Tolerant ##

!SLIDE bullets incremental

## Scales out easily ##

* Just add more nodes

!SLIDE

## Key-value Data Model ##

!SLIDE

## Content-Agnostic ##

!SLIDE

## Dynamo Distribution Model ##

!SLIDE

## Consistent Hashing ##

!SLIDE center

![Riak Ring](riak-ring.png)
 
!SLIDE bullets incremental

## Replication ##

* Tunable Consistency

!SLIDE

## Conflict Resolution using Vector Clocks ##

!SLIDE

## Vector Clocks ##

    <Mathias, 1>

!SLIDE

## Vector Clocks ##

    <Mathias, 1>, <Kresten, 1>

!SLIDE bullets incremental

## Vector Clocks - Siblings ##

    <Mathias, 1>, <Kresten, 1>

    <Mathias, 1>, <Tony, 1>

* Conflict!

!SLIDE bullets incremental

## Sane REST API ##

* Protobuffs Support for High Throughput

!SLIDE

## Ops-Friendly ##

!SLIDE center

![Riak Animated](riak_logo_animated1.gif)
