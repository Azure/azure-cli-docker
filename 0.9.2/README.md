# Microsoft Azure CLI Docker Image 

This Docker image has Microsoft Azure CLI installed and prepared. To run it, execute:

```bash
$ docker run -it microsoft/azure-cli
```

This will start a bash command prompt where you can run the `azure` command.

### How to persist configuration

In order to persist the login information and other preferences between runs,
make use of Docker volumes (`-v`) as follows:

```bash
$ docker run -it -v /.azure:/root/.azure microsoft/azure-cli
```

### More practical usage methods

Instead of running `docker run` command over and over again to execute Azure CLI
tasks, you can alias the command to `azure` (in Unix shells) as follows:

```bash
$ alias azure="docker run -it --rm -v /.azure:/root/.azure microsoft/azure-cli azure"
```

then run commands just like:

```bash
$ azure vm list
```

and the command will be executed in a Docker container.

------

### License

This project is distributed under [MIT License](LICENSE.md).
