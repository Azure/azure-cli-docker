# Microsoft Azure CLI Docker Image 

This Docker image has Microsoft Azure CLI installed and prepared. To run it, execute:

    $ docker run -v ~/.azure:/root/.azure -it microsoft/azure-cli [OPTIONS]

You can use this as a shell alias as well:
    $ alias azure='docker run -v ~/.azure:/root/.azure -it microsoft/azure-cli'
    $ azure [OPTIONS]
