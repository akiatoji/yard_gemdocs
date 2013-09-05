Run Yard server to serve Gem docs
===========

If you have Nginx running, you can run Yard server to serve rdocs for locally installed Gems.

*  Install nginx and passenger
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

* Add a localhost alias ```gems.doc``` to ```/etc/hosts``` file.   
* Restart nginx and access http://gems.doc:8010 to see docs.
* You'll need to re-start nginx everytime you add new gems to your Ruby installation.
