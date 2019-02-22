# Initialization

Copy a `docker-compose.yml`, `Dockerfile` and `.env` into your project root 

Edit `.env` file with the following content:

    appname=myapp

_note: Upon first run the first run during container creation `ng new ${appname}...` will be called_

# Development

For every day development...

    docker-compose up

Default docker compose `cmd` run the server.

Open http://localhost:4200/ on your HOST you will see the files running in the CONTAINER

## Tests

    docker-compose run angular ng test --browsers=ChromeHeadless

note: if you don't want to pass the --browsers flag everytime edit `myapp/src/karma.conf.js`

change

    browsers: ['Chrome'],

to

    browsers: ['ChromeHeadless'],

## Misc

### Interactive mode

You can run other `npm`, `ng` etc. command lines in interactive mode:

    docker ps
    docker exec -it <container_name> sh
    
    /srv/puffee # ng help

### Clean up docker

    docker system prune

or

    docker-compose down --rmi all
