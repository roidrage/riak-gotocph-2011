!SLIDE

# Basic Riak Usage #

!SLIDE smaller

# Simplified Data Structure #

    bucket:   gotocph
    key:      greeting
    value:    “<h1>Hi gotocph<h1>” 
    metadata: content-type=text/html

!SLIDE smallish

# Store Data #

    > PUT /riak/gotocph/greeting HTTP/1.1
    > User-Agent: curl/7.19.7 (universal-apple-darwin10.0)
    > Host: localhost:8098
    > Accept: */*
    > Content-Type: text/html
    > Content-Length: 18

!SLIDE smallish

    < HTTP/1.1 200 OK
    < X-Riak-Vclock: a85hYGBgzmDKBVIsTDb6JzOYEhnzWBmit8gf=
    < Vary: Accept-Encoding
    < Server: MochiWeb/1.1 WebMachine/1.7.2 (participate in the frantic)
    < Link: </riak/gotocph>; rel="up"
    < Date: Tue, 05 Oct 2010 14:38:40 GMT
    < Content-Type: text/html
    < Content-Length: 18

!SLIDE smallish

# Get Data #

    > GET /riak/gotocph/greeting HTTP/1.1
    > User-Agent: curl/7.19.7 (universal-apple-darwin10.0)
    > Host: localhost:8098
    > Accept: */*

!SLIDE smallish

    < HTTP/1.1 200 OK
    < X-Riak-Vclock: a85hYGBgzmDKBVIsTDb6JzOYEhnzWBmit8gf=
    < Vary: Accept-Encoding
    < Server: MochiWeb/1.1 WebMachine/1.7.2 (participate in the frantic)
    < Link: </riak/gotocph>; rel="up"
    < Last-Modified: Tue, 05 Oct 2010 14:38:40 GMT
    < ETag: 71hTllswGrWbI2O3WEkZYE
    < Date: Tue, 05 Oct 2010 14:40:04 GMT
    < Content-Type: text/html
    < Content-Length: 18
    < 
    <h1>Hi gotocph</h1>

!SLIDE bullets incremental

# Queries and Aggregation #

* MapReduce
* JavaScript or Erlang
* Riak Search

!SLIDE bullets incremental

# MapReduce #

* Map phases
* Reduce phases 

!SLIDE smaller

## Map Function ##

    @@@ javascript
    function(value, keydata, args) {
      var doc = Riak.mapKeyValuesJson(value)[0];
      if (doc.host.match(/basho\.com/)) {
        return [1];
      }
    }

!SLIDE smaller

## Reduce Function ##

    @@@ javascript
    function(values) {
      if (values.length > 0) {
        return [values.reduce(function(previous, current) {
          return previous + current;
        })];
      }
      else {
        return [0];
      }
    }

!SLIDE bullets incremental

## Links ##

* Connect Riak Objects
* Walkable

!SLIDE smaller

## Add Link ##

    > PUT /riak/gotocph/greeting HTTP/1.1
    > Link: </riak/gotocph/introduction>; riaktag="next"

!SLIDE smaller

## Walk Links ##

    > GET /riak/gotocph/greeting/_,next,_/ HTTP/1.1
