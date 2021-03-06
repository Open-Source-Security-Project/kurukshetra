# Kurukshetra &nbsp; [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Kurukshetra%20-%20A%20framework%20for%20teaching%20secure%20coding%20by%20means%20of%20interactive%20problem%20solving!&url=https://github.com/a0xnirudh/kurukshetra&via=a0xnirudh&hashtags=security,infosec,bugbounty,SecureCoding)

<p align="center">
  <img src="/staticfiles/img/logo.png" alt="Kurukshetra"/>
</p>

[![Github Release Version](https://img.shields.io/badge/release-V2.0-green.svg)](https://github.com/a0xnirudh/kurukshetra)
[![Github Release Version](https://img.shields.io/badge/php-7.2-green.svg)](https://github.com/a0xnirudh/kurukshetra)
[![License](https://img.shields.io/badge/License-GPL%20v3-green.svg)](https://github.com/a0xnirudh/kurukshetra/blob/master/LICENSE)
[![Kurukshetra loves Open source](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/a0xnirudh/kurukshetra)
[![Follow Kurukshetra on Twitter](https://img.shields.io/twitter/follow/kurukshetrahq.svg?style=social&label=Follow%20%40kurukshetra)](https://twitter.com/intent/user?screen_name=KurukshetraHQ "Follow Kurukshetra on Twitter")

**Kurukshetra** is a web framework that’s developed with the aim of being the first open source framework which provides a solid foundation to host reasonably complex **secure coding** challenges while still providing the ability to efficiently and dynamically execute each challenge on the basis of user input in a secure sandboxed environment.

Kurukshetra is composed of two components, the backend framework written in PHP, which manages and leverages the underlying docker system to provide the secure **sandbox** for the challenge execution, and the frontend, which is a user facing web app providing all the necessary controls, for the admin to host and modify the challenges , and the user to execute and view the result of each of his input.


## Detailed Tool Documentation:
> [https://docs.kurukshetra.io](https://docs.kurukshetra.io)

## Installation

### Supported Platforms

Kurukshetra has been tested both on **Ubuntu/Debian** (apt-get based distros) and as well as **Mac OS**. It should ideally work with any linux based distributions with PHP 7.2, MySQL and Docker (along with [remote API enabled](https://docs.docker.com/engine/api/v1.24/)) installed.

### Prerequisites:

There are a few packages which are necessary before proceeding with the installation:

* Git client: `sudo apt-get install git`
* PHP 7.2: Read the [instructions](https://askubuntu.com/a/856794) on how to install on ubuntu (along with php-curl - `sudo apt-ge install php7.2-curl php7.2-mbstring php7.2-mysql`)
* MySQL: `sudo apt-get install mysql-server`
* Docker: Read the [official installation](https://docs.docker.com/install/) guide (Also: [ubuntu installation](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04))
* Enable Docker API: Read - [How do I enable the remote Docker API](https://success.docker.com/article/how-do-i-enable-the-remote-api-for-dockerd)
* Create a folder `/var/config/` with write permission to `www-data` user


### Installing

Installing is as simple as moving the downloaded files into webroot:

```bash
git clone https://github.com/a0xnirudh/kurukshetra.git
cd kurukshetra
cp -r * /var/www/html/
chmod 755 -R /var/www/html
```

* Move all the files into webroot (which is usually `/var/www/html`): `cp -r kurukshetra/* /var/www/html`
* Give appropriate permissions for the moved files: `chmod 755 -R /var/www/html/`
* Give `challenges/uploads` directory write permissions for `www-data` user (see `uploads/README.md`).
* Visit `http://localhost` or `http://127.0.0.1` to navigate into installation (will auto redirect into /installation/).

<p align="center">
<img src="/staticfiles/img/install.png" width="700">
</p>

* Enter the MySQL DB credentials (user should have the permission to create database) and click on validate to see if the credentials are correct.
* Enter the Google OAuth `Client ID` and `Client secret` and make sure the redirect URL is set to the path `http://your-domain.com/login/index.php`

### Configuring Docker

Kurukshetra make uses of Dockers API's for running the user submitted code. A one time configuration is required before we can make use of the docker API's which is as follows:

* Pull the docker image: `docker pull phusion/baseimage:latest`
* Goto installation directory: `cd installation/optional/`
* Build kurukshetra image from the Dockerfile: `docker build -t kurukshetra .`

Alternatively, you can just run `python install.py` from within the directory `installation/optional` which will go ahead and install Docker (if not installed already) and will configure the Kurukshetra docker image automatically.

## Roadmap

The following are couple of ideas which we have in mind to do going ahead with Kurukshetra. If you have any ideas/feature requests which is not listed below, feel free to raise an [issue in github](https://github.com/a0xnirudh/kurukshetra/issues).

* Support for more languages including but not limited to JAVA, NodeJs and Ruby on Rails.

* Write more challenges along with unittests to cover all the  OWASP Top 10 vulnerabilities.

* Gamification of the whole framework by introducing scorebard based on challenge solving points (predefined points are already available for challenges based on difficulties).

## Screenshots

1. Challenge listing page:

<p align="center">
  <img src="/staticfiles/img/challenge_listing.png" alt="Kurukshetra"/>
</p>

2. Challenge solving page:

<p align="center">
  <img src="/staticfiles/img/challenge_solving.png" alt="Kurukshetra"/>
</p>

3. Admin portal (statictics):

<p align="center">
  <img src="/staticfiles/img/admin_dashboard.png" alt="Kurukshetra"/>
</p>

4. Admin challenge edit/add challenges:

<p align="center">
  <img src="/staticfiles/img/admin_challenge_page.png" alt="Kurukshetra"/>
</p>


## Video demo (Admin Functionalities)

<div align="center">
  <a href="https://www.youtube.com/watch?v=yrfmyz3p9a4" target="_blank"><img src="/staticfiles/img/video_thumbnail.png" alt="Kurukshetra Admin functionalities"></a>
</div>


## Contributors

Awesome people who built this project:

##### Lead Developers:

Anirudh Anand ([@a0xnirudh](https://twitter.com/a0xnirudh))  
Mohan KK ([@MohanKallepalli](https://twitter.com/MohanKallepalli))  

##### Project Contributors:

Arjun T U ([@arjunkikz](https://twitter.com/arjunkikz))  
Durga Subramanian ([@0xdug](https://twitter.com/0xdug))  
Ankur Bhargava ([@_AnkurB](https://twitter.com/_AnkurB))  
Prajal Kulkarni ([@prajalkulkarni](https://twitter.com/prajalkulkarni))  
