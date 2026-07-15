To create a custom Ansible Execution Environment on MacOS with Docker installed:

1. Create a local "custom-ansible-ee" folder and download the following files:
- execution-environment.yml
- requirements.yml
2. Execute the command "sudo pip3 install ansible-builder" to install ansible-builder (python required)
3. Go to the folder and execute the command "ansible-builder create" to generate the build context 
4. Then execute the command "docker buildx build --platform linux/amd64 -t <your-registry>/awx-custom-ee:v1.0.0 ./context --load" to build the Ansible EE image
5. Make sure your logged in Docker Hub with "docker login <your-registry>"
6. Then push the image to your registry with "docker push <your-registry>/awx-custom-ee:v1.0.0"
7. Final step is to import the custom EE into AWX by entering your registry credentials in AWX and then add EE
