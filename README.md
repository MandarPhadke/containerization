# containerization

        Steps for Setting Up a Basic HTML Page with Nginx Using Docker Compose

1. Basic HTML Page
   
   Created on basic html page.

2. Nginx Configuration
   
   - Created a configuration file named `nginx.conf` that will serve the `index.html` page.
   - Configured Nginx to listen on port 80. Example content for `nginx.conf`:

3. Dockerfile
   
   The `Dockerfile` defines the Docker image and uses the official Nginx base image. Follow these steps to create the `Dockerfile`:

   - Use the official Nginx image as the base.
   - Copy the `index.html` file and the `nginx.conf` configuration file into the appropriate directories inside the container.
   - Ensure that the Nginx server starts when the container is run.

4. Docker Compose File (docker-compose.yml)
   
   Docker Compose can be used to manage the build and deployment of your Nginx service. The `docker-compose.yml` file simplifies multi-container applications or services like this one.

   - This Compose file builds the Docker image from the `Dockerfile` and maps port 80 of the container to port 80 on the host machine.
   - It also mounts the local `index.html` and `nginx.conf` files into the container to ensure that the Nginx server uses the correct configuration and content.

5. Building and Running the Docker Image
   
   After creating the necessary configuration files and the Dockerfile, follow these steps to build and run the image using Docker Compose:

   1. Build the Docker Image:
   
      Ensure that you're in the correct directory, where the `docker-compose.yml` and `Dockerfile` are located, and run the following command to build the image:

      bash
      docker-compose up -d

   2. Verify the Service:

      After the image is built and the container is running, open a browser and go to `http://localhost`. You should see the content of `index.html` displayed (e.g., "Hello, Docker!").
      Alternatively, you can use `curl` to test the service from the command line:
      bash
      curl http://localhost
      This will output the content of `index.html`.


pushing the docker file to ECR.

aws is already configured, created ECR repo using command below.
aws ecr create-repository --repository-name mandar_docker_assignmenr

![image](https://github.com/user-attachments/assets/dd674566-4a3c-470d-afb2-96de1a22bfa5)

ECR Created
![image](https://github.com/user-attachments/assets/b8272830-094a-4c3b-b4c2-fc4a1e0783ca)

clicked on the “View push commands” button.
![image](https://github.com/user-attachments/assets/75963bd5-8b52-406d-84dd-d8abbbe38b1d)

used an authentication token and authenticate your Docker client to your registry. Use the AWS CLI:
![image](https://github.com/user-attachments/assets/8a2a25cd-886a-4ecb-bbc2-d17ef5fceeff)

once connection is done, just push docker image to ECR        
sudo docker tag my-nginx-image:latest 975050024946.dkr.ecr.us-west-2.amazonaws.com/mandar_docker_assignmenr:latest

pushing the image to ECR.
docker push 975050024946.dkr.ecr.us-west-2.amazonaws.com/mandar_docker_assignment:latest
![image](https://github.com/user-attachments/assets/10c62c2d-cfa5-4b6a-a48d-1b995d0a552b)

it's added in ECR.
![image](https://github.com/user-attachments/assets/43e6dccd-b86f-4f08-9cdf-3d8272f49843)












  
