# Pwndocker 18.04 Manual

### Build the image from Dockerfile

```
make build
```

### Start up the docker

* By default if you run like this the mount folder will be your current working directory, you can also use this command if you want to restart docker.
```
make run
```

* If you want to specify another mounting folder, please add MNTDIR environement variable.
```
MNTDIR=<your-mount-folder> make run
```

### Stop the docker

```
make stop
```

### Interact with docker

```
make exe
```
