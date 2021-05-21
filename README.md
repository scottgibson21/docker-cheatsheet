# docker-cheatsheet

## Images

### Build an image

```powershell
docker build -t "<repo>:<tag>" .
```

### Gotchas

- React Dev: You cannot bind to container port `80` when dockerizing react app in dev (served from Node.js, default for react scripts start).  On linux systems running on any port below `1024` requires root access, which Node.js does not have. Attempting to run with `-p 3000:80` will not work, but `-p: 3000:3000` will.
