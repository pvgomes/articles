+++
date = '2019-10-17T11:30:39+02:00'
draft = false
title = 'Running Clojure Locally With Docker 2019 10 17'
+++

I started working with docker in 2013 and at that time, to be honest, I use docker like a virtual machine, or maybe you know the famous vagrant as a wrapper for virtual machines to local development environment. After 2016 I decided only to install on my local machines the docker and docker-compose and if I need to install any services or languages like PHP, Ruby, Go, Redis, RabbitMq…(well long list) I should wrap it on docker.

Well done, that's my life, always simple, always easy to made changes, easy to change from nodejs 6.x to nodejs 10.x without using stuff like nvm or n, no problem with new PHP versions or even that boring services in my host machine making it to dirty and sometimes conflicting in weird ways. I never faced a big challenge for that, it's always simple and quick to start coding and making some proofs of concept.

But in 2019 when I started on Clojure world it seems very confusing to me, the way that usually we use local environment with REPL seems a different challenge to me, but to be honest, simple if a take some time to make my own development environment with clojure and stuffs like REPL and leiningen together. And I think that would be great if I show to you guys how I did it simple (maybe not).

Ok, let's start, the idea here is to create a Clojure project having only docker and docker-compose installed in our machine ok?

Zoom image will be displayed

Please before the start, install Docker and docker-compose in your machine.

Ok, let's create a path where we'll add our project lets call it "clojure-projects"

mkdir clojure-projects
Now get our full path of this project, access it and type

pwd
In my case the full path is:

/Users/pvgomes/clojure-projects
Ok, lets up a docker container using docker run now, something like this

docker run -v /Users/pvgomes/Projects/pocs/clojure-projects:/clojure-projects -p 127.0.0.1:5000:5000 -i -t clojure:openjdk-11 /bin/bash
What does this command do?
we run a docker container mapping the clojure projects path to one path that we're creating inside a container in "/clojure-projects" it will map our host path to container path, we also say that we want to listen the port 5000 and use one of the official clojure containers.

It will take some time (depends on your connection) and then will connect you to container bash, something like this:


first docker access
Go to clojure path which is mapped to our host machine:

cd /clojure-projects/
Ok, now we can create our first project using lein, we'll call this project cpizza (meaning clojure pizza, a simple app where the customers can request pizzas and maybe we'll do it fully for the next articles)

lein new compojure cpizza
Access the new created path (pizza)

cd cpizza
Now let's run the project on port 5000

lein ring server-headless 5000
You should see something like this (it will take some minute depends on your internet connection):

Zoom image will be displayed

And then, just try to access in your browser at http://127.0.0.1:5000

The result is something like this


Or by curl


Great, we can run our Clojure project without having clojure or leiningen installed on our local environment.

But wait, I would like to run REPL in our IDE, how?

In the next article, I'll show you how ok?