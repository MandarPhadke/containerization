# containerization

        Steps for Setting Up a Basic HTML Page with Nginx Using Docker Compose

1. Basic HTML Page
   
   The HTML page code is available in a Git repository. Ensure the `index.html` file is created with the required content, such as "Hello, Docker!".

2. Nginx Configuration
   
   - Create a configuration file named `nginx.conf` that will serve the `index.html` page.
   - Configure Nginx to listen on port 80. Example content for `nginx.conf`:

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

  
