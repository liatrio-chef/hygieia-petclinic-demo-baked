hygieia-petclinic-demo-baked
========================
A baked vagrant box from wrapper cookbook hygieia-petclinic-demo-unbaked that has hygieia installed and mock data in a local mongodb.

* Timestamps are updated hourly in the mongodb on cron from /home/vagrant/update_timestamps.rb

Instructions:
* Unbaked https://github.com/liatrio-chef/hygieia-petclinic-demo-unbaked
* Baked https://github.com/liatrio-chef/hygieia-petclinic-demo-baked

Requirements
------------
Vagrant 1.8.1

Usage
-----

* `git clone https://github.com/liatrio-chef/hygieia-petclinic-demo-baked.git`

* `cd hygieia-petclinic-demo-baked`

*  `vagrant up`

* Browse to [http://localhost:13000/](http://localhost:13000/)

* Click in the user field and wait for API Connectivity to change from red to green (5-30 seconds depending on network quality / cloud)

* Login with admin / password

* When browsing to a dashboard it can take up to 10-20 seconds for the "Build Per Day" and "Build Duration" graphs to populate.

Updating the box
------------------
* Check to see if you have an existing version of the box: `vagrant box list| grep liatrio/hygieia-petclinic-demo-baked` if so you'll get output like this:
```
liatrio/hygieia-petclinic-demo-baked                    (virtualbox, 0.0.1)
```

* If you do have an existing version, remove it: `vagrant box remove liatrio/hygieia-petclinic-demo-baked --box-version 0.0.1`

License and Authors
-------------------
Authors: Drew Holt <drew@liatrio.com>
