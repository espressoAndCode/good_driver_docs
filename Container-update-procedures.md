# Container update procedures

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

