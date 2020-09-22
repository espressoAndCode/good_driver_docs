# Container update procedures

### Clear out the Existing Docker Artifacts

1. Stop all running containers
```
docker-compose down
```

2. Remove all stopped Docker containers. (Select 'y' at the warning message)
```
docker container prune
```

3. Remove all unreferenced Docker volumes. (Select 'y' at the warning message)
```
docker image prune
```

4. Remove all unused Docker networks. (Select 'y' at the warning message)
```
docker network prune
```

5. Rebuild the setup.
```
docker-compose build 
```

6. Run the new setup.
```
docker-compose up
```

### Create the database

```
$ docker-compose exec server python manage.py recreate_db
```

### Seed the database
```
$ docker-compose exec server python manage.py seed_db
```
---

This should do the trick!