# drupal8. Module development.

Drupal 8 repository based on the docker4drupal  
https://github.com/wodby/docker4drupal

Installed Drupal standard profile with pre-installed exmaples module:  
https://www.drupal.org/project/examples

## How to start development:

#### Requirements:  
Docker: https://www.docker.com/  
Docker-compose: https://docs.docker.com/compose/install/  
git: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

#### Starting the environment:  
***1. Clone the repository***
```
git clone https://github.com/dmndvs/drupal8.git
cd drupal8
```

***2. Run the containers***
```
docker-compose up -d
```

***3. Run composer and drupal required commands inside the docker container***

 MacOS, Linux
```
make shell
composer install
drush cr
drush updb -y
drush cim -y
```
 Windows
```
docker exec -ti drupal8_php sh
composer install
drush cr
drush updb -y
drush cim -y
```
> If you are using mintty, try prefixing the command with 'winpty':   
> `winpty docker exec -ti drupal8_php sh`

***4. Check the results in the browser:***  

http://drupal.docker.localhost:8000/

if everything is ok, you will se the instance of the drupal.