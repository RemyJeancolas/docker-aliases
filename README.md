# docker-aliases
Just a set of docker aliases to make developers life easier.  
This repository will be updated as needed, feel free to propose your own aliases.

## Node.js / Npm

To use `node` and `npm` commands from host with docker, simply add these aliases in your .bashrc file:
```bash
# Specify node environment
node_env='development'

# Specify docker image to use
node_image='nodesource/node'

# Add extra parameters if needed
node_args='-p 80:80 -p 8080:8080'

# Aliases
alias npm="docker run --user $(id -u):$(id -g) -it --rm -e HOME=$HOME -e NODE_ENV=$node_env -v
$HOME:$HOME -v $(pwd):/usr/app/ -w /usr/app $node_args $node_image npm"
alias node="docker run --user $(id -u):$(id -g) -it --rm -e HOME:$HOME -e NODE_ENV=$node_env -v
$HOME:$HOME -v $(pwd):/usr/app/ -w /usr/app $node_args $node_image node"
```
