# Container update procedures
### Set the following environment variable

This defines the base URL for AJAX requests from the React app. 
 
```
$ export REACT_APP_USERS_SERVICE_URL=http://localhost:5001
```
**PRO TIP** - put this in your `.bashrc` file so you don't have to enter it every time you open a shell. It becomes a pain, and I promise that you'll forget.

If you do it this way, be sure to add double quotes around the value like this:
```
export REACT_APP_USERS_SERVICE_URL="http://localhost:5001"
```

### Clear out the Existing Docker Artifacts

1. Stop all running containers
```
docker-compose down
```

2. Delete all containers using the following command:
```
docker rm -f $(docker ps -a -q)
```

3. Delete all volumes using the following command:
```
docker volume rm $(docker volume ls -q)
```

4. Rebuild the setup.
```
docker-compose build --no-cache 
```

5. Run the new setup.
```
docker-compose up
```

### Create and seed the database

```
$ docker-compose exec server python manage.py reset_db
```

