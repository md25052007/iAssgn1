\# Assignment 2 — Create \& Run Two Containers That Communicate



\*\*Goal:\*\* Deploy two containers — one static web server and one simple API — and connect them using Docker networking.



\*\*Approach:\*\* Created a custom Docker network `webnet` so containers can communicate using container names. Built a static web server container using Nginx. Ran a simple API container using `hashicorp/http-echo`. Verified communication between containers using `curl` from the web container.



\*\*Steps and Commands:\*\*



1\. Create Docker network:

docker network create webnet



2\. Build and run web container:

\- Dockerfile:

FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html



\- Build image:

docker build -t web .



\- Run container:

docker run -d --name web --network webnet -p 8080:80 web



3\. Run API container:

docker run -d --name api --network webnet hashicorp/http-echo -text="Hello from API" -listen=:5678



4\. Test connectivity inside web container:

docker exec -it web curl http://api:5678



\*\*Expected output:\*\*

Hello from API





