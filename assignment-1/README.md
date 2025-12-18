\# Assignment 1 — Build \& Run a Personalized Web Server Container



\## Approach

A simple static website was created using HTML and served through an Nginx web server inside a Docker container.

Docker was used to build a custom image, run the container with port mapping, verify accessibility, and then clean up resources.



\## Instructions and Commands Used



1\. Create project directory and move into it:

&nbsp;  mkdir maithreya-site

&nbsp;  cd maithreya-site



2\. Create the HTML file:

&nbsp;  notepad index.html



3\. Create the Dockerfile:

&nbsp;  notepad Dockerfile



4\. Build the Docker image:

&nbsp;  docker build -t maithreya-site .



5\. Run the container on host port 7070:

&nbsp;  docker run -d -p 7070:80 --name maithreya-container maithreya-site



6\. Test the application:

&nbsp;  Browser: http://localhost:7070  

&nbsp;  Curl: curl http://localhost:7070



7\. Stop and remove the container:

&nbsp;  docker stop maithreya-container

&nbsp;  docker rm maithreya-container



