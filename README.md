# docker-bootstrapped-mysql
A simple docker container that is bootstrapped with data that is provided.  This is great for simple LAMP projects that need to bootstrap Wordpress, Joomla or Drupal.  Or anything else that just needs a simple database that is bootstrapped with no other configuration changes.

## Understanding the tagging system
The *tag_name* should be replaced with the following format \<host (optional - add if not pushing to dockerhub)\>/\<username (optional - add if pushing to personal repository)\>/<name> :

## Building the image
1. Put a sql file called *export.sql* containing your exported data into the folder *data*.
2. From the root directory of the git repository, execute the following (substituting the tag name).
```
docker build -t <tag_name> .
```

## Deploying the image
You can push this image to a container using the command.  It will know which server to push to because the host must be in the tag name.

```
docker push <tag_name>
```
