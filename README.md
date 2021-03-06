# irontools/ferrum

### Compact and versioned dev container with dumb-init, supervisor, node, mongo, nvm, zsh, code-server.

## How to run

```
docker run -it \
  -p 3000:3000 \
  -p 5000:5000 \
  -p 5500:5500 \
  -p 27019:27017 \
  -p 8443:8443 \
  -v "$(pwd)":"/coder/project" \
  --name ferrum \
  dimitrijd/iron
```

## How to restart after exit

```
docker start ferrum && docker attach ferrum
```

## How to attach a new terminal session

```
docker exec -it ferrum zsh
```

## TODOs

#### Help

- [x] add welcome intro
- [ ] add global packages from npm (debug etc)

#### Host-side helpers

- [ ] managing container status via helper function (pull, run, start, stop, restart)
- [ ] sharing .ssh github mail / name
- [ ] managing mongodb export / import
- [ ] code-space compatible

#### Permissions

- [ ] UID/GUI from linuxserver.io

#### Home

- [ ] XDG compliant
- [ ] $HOME/.ferrum can create the container
- [ ] divide build context into base / stack / dev (inside each build / run)

#### Versioning

- [ ] add versionning to apt-packages via `requirements.txt`

#### Build options

- [ ] options base: ubuntu | debian | alpine
- [ ] options overlay: dumb-init+supervisord | s6 overlay
- [ ] options stack: node+mongo | node+Postgres | node+Mysql | node+sqlite3
- [ ] options dev: code-server | vim
