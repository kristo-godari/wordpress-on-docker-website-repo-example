# WordPress on Docker - Website Repository Example

This is an example respository for [Wordpress on Docker](https://github.com/kristo-godari/wordpress-on-docker) project. In order for that to work properly a specific structure is needed. 
Your website repo needs to have the following folders and files in the root:
- env
  - ansible-inventory - used to store ansible inventory
    - local.yml
    - prod.yml
  - build.yml - used for build process
  - common.yml - used for common operation like build and deploy
  - deploy.local.yml - used to deploy locally
  - deploy.prod.yml - use to deploy in production
- ssl-certs - used for SSL
  - ssl.crt
  - ssl.key
- ssh - Used to connect to prod server
  - prod-key.pem
- wp-content - Used for custom wordpress files, ex: you have a custom plugin, or theme that you develop.

## How to use
This project is meant to have a git submodule for the deployment, check deployment repository here: [Wordpress on Docker](https://github.com/kristo-godari/wordpress-on-docker) 

## Replace placehoders
Under the env folder all files have {placeholder} variable. Replace this with real values. 

## Add ssh key
Update the ssh/prod-key.pem with the your production ssh key.

## Add SSL certificate and key
Update the ssl-certs/ssl.crt with the SSL certificate.
Update the ssl-certs/ssl.key with the SSL key.


## Add git submodule
- Make sure you don't have a deployment folder.
- Create submodule `git submodule update --init --recursive`. This will create the deployment folder and clone the git repo inside.
- If this does not work to add the submodule, you can try:
  - `git submodule add https://github.com/kristo-godari/wordpress-on-docker deployment`
  - `git submodule update --init --recursive`