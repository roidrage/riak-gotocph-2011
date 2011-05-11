!SLIDE bullets

# Mass Storage #

!SLIDE bullets

# Social Media #

* Tweets
* Links
* Website Archives

!SLIDE bullets incremental

## Data Model ##

* Blobs (Content-Typed)
* Well-Known Keys
* Links for Relationships

!SLIDE smaller

## Tweets ##

### Key: Tweet ID ###
### Content: ###

    {
      "text": "Tweeting live from my talk at #gotocph",
      "user": {
        "screen_name": "roidrage"
      }
      "created_at":"Thu May 12 10:50:58 +0000 2011",
      "id_str": "67953117043499008",
    }

!SLIDE bullets

## Websites ##

* Key: gotocon.com/cph-2011
* Content: Blob with text/html

!SLIDE bullets incremental

## Relationships ##

* Prefilter Web Links, Tweet Relationships
* Store as Riak Links

!SLIDE bullets incremental

## Links ##

* Connect Websites
* Twitter Replies
* Twitter Users' Tweets

!SLIDE smallest

    Link: </riak/websites/gotocon.com%2Faarhus-2011>; riaktag="external"

!SLIDE smallest

    Link: </riak/tweets/41212010>; riaktag="in_reply_to"

!SLIDE smallest

    Link: </riak/twitter_users/roidrage>; riaktag="owner"

!SLIDE bullets incremental

## Lookup ##

* Secondary Indexes
* Full Text Search

!SLIDE bullets incremental

## Riak Search ##

* Distributed Full Text Search
* Solr-Compatible API
* Integrated with Riak KV

!SLIDE bullets incremental

# Use Case: Linkfluence #

* Hundreds of GB Data Stored Every Day
* Content and Metadata in Riak
* Indexed with Postgres, Solr and ElasticSearch
