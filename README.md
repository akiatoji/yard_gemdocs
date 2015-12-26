Run Yard server to serve Gem docs
===========

## Motivation

I started working at an office close to the beach.  I'd go work on the beach but there is no free WiFi 
which means you can't lookup nicely formatted rdocs.

### UPDATE

I quit the job at the office near the beach some time ago.  Location was great, people not so much, with some exception. 

## Solution

Run local Yard server to serve rdocs for locally installed Gems.

## Step by step 

*  Install nginx and passenger
*  Check out this project
*  Run 'bundle install'
*  Add the following to nginx.conf 

```nginx
server {
      listen 8010;
      server_name gems.doc;
      root /wherever/yard_gemdocs/public;
      rails_env development;
      passenger_enabled on;
}
```

* Add localhost alias ```gems.doc``` to ```/etc/hosts``` file.   
* Restart nginx and access http://gems.doc:8010 to see docs.
* Now go to the beach and code all day.
* Drinks with little umbrellas optional.
* List of local gems are built at nginx startup.  You'll need to re-start nginx everytime new gems are added.
