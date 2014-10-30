docker-meteor
=============

Docker automatic build for meteor development, including SSH and Samba servers (mostly for Mac OS X and Windows)

Usage
-----

To create the image, execute the following command on the tutum-docker-lamp folder:

	docker build -t kossoy/meteor .


Running your Meteor docker image
--------------------------------

Start your image binding the external ports 3000 (meteor-dev), 445 (samba) and 22 (ssh) in all interfaces to your
container:

	docker run --name <container name> -d -p 3000:3000 -p 2222:22 -p 445:445 -p kossoy/lamps


Connecting to the ssh server
-----------------------------

The first time that you run your container, a random password will be generated
for user `root`. To get the password, check the logs of the container by running:

	docker logs <CONTAINER_ID>

You will see an output like the following:

	========================================================================
	You can now connect to this Ubuntu container via SSH using:

	    ssh -p <port> root@<host>
	and enter the root password 'U0iSGVUCr7W3' when prompted

	Please remember to change the above password as soon as possible!
	========================================================================

In this case, `U0iSGVUCr7W3` is the password allocated to the `root` user.

Thanks to https://github.com/tutumcloud/tutum-ubuntu
