# Jenkins and Sonarqube in Docker

## How to
### Run Jenkins container
- Dockerfile in this folder can be used to generate the image:
<pre><code>docker build -t djenkins .</code></pre>

- Run container using next command:
 <pre><code>docker run --name jenkins-docker -d -p 8080:8080 -p 50000:50000 -v /home/vagrant/Jenkins_Home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock djenkins</code></pre>

 - Check container running:
<pre><code>docker ps</code></pre>

- Obtain Jenkins password running next command:
<pre><code>docker exec <CONTAINER_ID> cat /var/jenkins_home/secrets/initialAdminPassword</code></pre>

- Download next plugins: 
    - Docker
    - Docker Pipeline
    - Docker API
    - Sonar Scanner

### Run Sonarqube container (only for POC purposes)

- Run container using next command
<pre><code>docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube</code></pre>

- Login first time in dashboard you need to use user: admin, password: admin and will ask for change