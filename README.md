# docker-bootstrapped-mysql
A simple docker container that is bootstrapped with data that is provided.  This is great for simple LAMP projects that need to bootstrap Wordpress, Joomla or Drupal.  Or anything else that just needs a simple database that is bootstrapped with no other configuration changes.

None of this is extremely complicated, but it is easier to use this than to recreate it every time you randomly need it.

## Understanding the tagging system
The *tag_name* should be replaced with the following format \<host (optional - add if not pushing to dockerhub)\>/\<username (optional - add if pushing to personal repository)\>/<name> :

## Building the image
1. Put a sql file called *export.sql* containing your exported data into the folder *data*.
2. From the root directory of the git repository, execute the following (substituting the tag name).
```
docker build -t <tag_name> .
```

## Running the Container
At this point, we are just going to define the port proxy and then set all the usernames and password and start the database.  The MySQL instance will execute your exported sql in the database you specify.

```
docker run -it -p3306:3306 -eMYSQL_ROOT_PASSWORD=<root_password> -eMYSQL_USER=<sql_user> -eMYSQL_PASSWORD=<user_password> -eMYSQL_DATABASE=<database_name> <tag_name>
```

At this point, you can connect remotely with any number of systems.

## Connecting to ths Instance
The simple command for connecting to the instance from another server is the following:

```
mysql -h<server_name> -u<user_password> -p -D<database_name>
```

Note that you will be prompted for your user password.

## Deploying the image
You can push this image to a container using the command.  It will know which server to push to because the host must be in the tag name.

```
docker push <tag_name>
```

