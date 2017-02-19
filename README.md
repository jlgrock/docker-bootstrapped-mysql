# docker-bootstrapped-mysql
A simple docker container that is bootstrapped with data that is provided.  This is great for simple LAMP projects that need to bootstrap Wordpress, Joomla or Drupal.  Or anything else that just needs a simple database that is bootstrapped with no other configuration changes.

To load the data, put a sql file called *export.sql* containing your exported data into the folder *data*.


## In case you need help understanding the tagging system
The *tag_name* should be replaced with the following format \<host (optional - add if not pushing to dockerhub)\>/\<username (optional - add if pushing to personal repository)\>/<name> :

## Building the image
To build the container, execute the following (substituting the terms in brackets).  
```
docker build -t <tag_name> 
```
## Deploying the image
Similarly, you can push this image to a container using the command
```
docker push
```
