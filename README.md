# Docker Environment for Magento 2 Development
## Prerequisites
- You must have docker installed on your system:  [macOS Installer](https://docs.docker.com/desktop/mac/install/) *(required)*
- For a better performance on macOS docker-magento use [docker-sync](http://docker-sync.io/) *(optional)*
-- `sudo gem install docker-sync`
## Installation
1. Clone the website file repository into your working directory
2. Add `dm` to your aliases file
`alias dm=".dm/bin/dm"`  
3. Clone docker-magento into a `.dm` directory in the Magento root
`git clone git git@github.com:danhort/docker-magento.git .dm`   
4. Initialize the environment with available PHP versions (7.3 or 7.4 or 8.1)
`dm --init-sync <PHP version>` or `dm --init <PHP version>`  
5. Create the new container
`dm start`
6. Copy files to container (not needed with docker-sync or on linux)
`dm copytocontainer --all` 
7. Run composer
`dm composer install`
8. Import your database
`dm db-import <absolute path to sql file> (it can be gzipped)`

## Usage  
Full list of available options can be found by running: `dm --help`

## Links
Magento: https://magento.localhost   
phpMyAdmin: http://localhost:8080   
MailHog: http://localhost:8025    
