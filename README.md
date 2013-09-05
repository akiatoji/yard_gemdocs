Run Yard server to serve Gem docs
===========

If you have Nginx running, you can run Yard server to serve rdocs for locally installed Gems.

1.  Install nginx and passenger
1.  Run 'bundle install'
3.  Add the following to nginx.conf 
```server {
      listen 8010;
      server_name gems.doc;
      root /wherever/yard_gemdocs/public;
      rails_env development;
      passenger_enabled on;
}```
4. Add a localhost alias ```gems.doc``` to ```/etc/hosts``` file.   
5. Restart nginx and access http://gems.doc:8010 to see docs.
6. You'll need to re-start nginx everytime you add new gems to your Ruby installation.
