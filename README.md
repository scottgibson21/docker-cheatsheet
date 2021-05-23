# docker-cheatsheet

## Images

### Build an image

```powershell
docker build -t "<repo>:<tag>" .
```

### Gotchas

- React Dev: You cannot bind to container port `80` when dockerizing react app in dev (served from Node.js, default for react scripts start).  On linux systems running on any port below `1024` requires root access, which Node.js does not have. Attempting to run with `-p 3000:80` will not work, but `-p: 3000:3000` will.

## Docker Compose

### Gotchas

- docker compose will append "project" (parent directory) to all containers and volumes.  To prevent this from happing on named containers you can adding the following cofiguration in the `volumes` section in the `docker-compose` file:

```json
volumes:
  <volume name>:
    driver: local
    name: <volume name>
```
