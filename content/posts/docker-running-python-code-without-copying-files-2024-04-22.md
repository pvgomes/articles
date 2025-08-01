+++
date = '2024-04-22T11:49:15+02:00'
draft = false
title = 'Docker Running Python Code Without Copying Files 2024 04 22'
+++
![](https://miro.medium.com/v2/resize:fit:700/0*Ej9M6BSAgPKv9Qti.jpg)

I never liked the idea to messy all installations in our host computer to run any kind of programming language, mainly because they are in constant change and evolution and the projects that we work as a software engineer not necessarily follow the same evolution, thus makes our life even more challenging if we’re working in different projects. Nowadays most of the things related to docker, kubernetes or containers will focus on production purpose, but I remember year ago in the very beginnings of docker where the main idea is to solve the messy of different local environments(ow god, look at me using this elder sentence), well, this article is focusing on setting a simple environment where you can have you python code running using a docker and dont needing to worry about version on your local machine. Yes I don’t like solutions like Pyenv, but this is my personal point of view ok?

That said, I want to have a Docker container that runs Python scripts from a local directory without copying the scripts into the container, for that we will use Docker volumes to mount the local directory into the container. This setup allows you to edit the scripts on your local machine and have the changes immediately available inside the Docker container.

It is very simple, let me show to you, step by step

Does anyone know how to display a local image in markdown? I don’t want to set up a webserver for that.

I try the following in markdown, but it doesn’t work:

1. 1.  **Install Docker**: Ensure that Docker is installed on your machine. You can download it from [Docker’s official website](https://www.docker.com/get-started).
1. 2.  **Create a Directory for Your Python Scripts**: Create a directory on your local machine where you will store your Python scripts. For example:

\# Use the official Python image from the Docker Hub FROM python:3.9 # Set the working directory in the container WORKDIR /usr/src/app # Install any dependencies if necessary (optional) # COPY requirements.txt ./ # RUN pip install --no-cache-dir -r requirements.txt # Command to keep the container running CMD \["tail", "-f", "/dev/null"\]

docker run -d --name my\-python-container -v /Users/YOUR-USER/my\-scripts:/usr/src/app my\-python-runner

About the command:  
\-d: Runs the container in detached mode.  
— name my-python-container: Names the container for easier reference.  
\-v /Users/YOUR-USER/my-scripts:/usr/src/app: Mounts the local directory /Users/YOUR-USER/my-scripts to the container’s /usr/src/app directory.

For example, to run hello.py:

Now you can run all python code you want!

# Conclusion

Managing multiple programming environments on a host computer can get messy, especially when different projects require different setups. Docker offers a clean solution by using containers to keep everything isolated and organized.

Originally designed to simplify local development, Docker can still help us avoid installing multiple versions of Python or other tools directly on our machines. Instead, we can run Python scripts in a Docker container and keep our local environment tidy.

The recap on what we did or our nutshell version:

1. 1.  **Install Docker**: Make sure Docker is installed on your computer.
1. 2.  **Create a Scripts Directory**: Set up a local folder for your Python scripts.
1. 3.  **Write a Dockerfile**: Use this simple Dockerfile to create a Python environment:

FROM python:3.9 WORKDIR /usr/src/app CMD \["tail", "-f", "/dev/null"\]

docker run -d --name my\-python-container -v /path/to/your/scripts:/usr/src/app my\-python-runner

I love docker, besides the powerful that it offers on production you can easily manage and run your everything without worrying about installing and configuring on your local machine. This keeps your development environment clean and hassle-free. Enjoy coding!