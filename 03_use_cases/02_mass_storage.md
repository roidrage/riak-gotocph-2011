!SLIDE

# Social Media #

* Tweets
* Links
* Website Archives

!SLIDE bullets incremental

## Data Model ##

* Blobs (Content-Typed)
* Well-Known Keys
* Links for Relationships

!SLIDE

## Tweets ##

    {
      "text": "Tweeting live from my talk at #gotocph",
      "user": {
        "screen_name": "roidrage"
      }
      "created_at":"Thu May 12 10:50:58 +0000 2011",
      "id_str": "67953117043499008",
    }

!SLIDE

## Websites ##

* Key: `gotocon.com/cph-2011`
* Content: Blob with text/html

!SLIDE bullets incremental

## Relationships ##

* Prefilter Web Links, Tweet Relationships
* Store as Riak Links

!SLIDE

## Links ##
