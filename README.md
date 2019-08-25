The goal of this project was to create a Python server running Flask to act as an RESTful API for controlling a swarm of docker containers, allowing the users to carry out the following commands through the API.

1. GET /containers - List all containers

2. GET /containers?state=running - List running containers (only)

3. GET /containers/\<id\> - Inspect a specific container

4. GET /containers/\<id\>/logs - Dump specific container logs

5. GET /images - List all images

6. POST /images - Create a new image

7. POST /containers - Create a new container

8. PATCH /containers/\<id\> - Change a container's state

9. PATCH /images/\<id\> - Change a specific image's attributes

10. DELETE /containers/\<id\> - Delete a specific container

11. DELETE /containers - Delete all containers (including running)

12. DELETE /images/\<id\> - Delete a specific image

13. DELETE /images - Delete all images


### Setup

1. Initialise the manager instance by running: 'docker swarm init'.

2. Join the workers to the swarm by running: 'docker swarm join --token' followed by the token supplied by the manager
	
3. Run DockerCMS.py, it is the server managing all of the API endpoints, executing the required code for each command and returning the relevant results to the user.
	
4. Create multiple replicas by running: 'docker service create --replicas 5 -p 80:80 --name web nginx' on the manager. The status can be viewed on the visualizer.
	  
5. cmsTester is a batch file designed to test each feature of DockerCMS.py using curl commands.
Some tests will run automatically, for others it will ask for input of IDs or states to change, the ids can be taken from the previous commands output.
	   
![Video Demonstration](https://youtu.be/byXBfS57IKk "Video Demonstration")

