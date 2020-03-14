# docker_express

### Get started locally
1. Pull repo: `git@github.com:david-potgieter/docker_express.git`
2. Install deps: `yarn install`
3. Start server: `yarn start`

### Initiliase/Install Docker
1. Install docker:
   1. Windows: https://docs.docker.com/docker-for-windows/install/
   1. Mac: https://docs.docker.com/docker-for-mac/install/
2. Pull this repo container: `docker pull potgied/docker_express:latest`
3. Run this container locally: `docker run -dt potgied/docker_express`
  3. You should be able to interrogate the status by checking `docker images`
  3. Use the container ID provided to run `docker logs ##containerID##`
  3. You should see "Running on http://0.0.0.0:8080"
  3. Visit http://0.0.0.0:8080 and see `{ message: "Hello Docker World" }`
4. If all is working you can shut it down: `docker stop ##containerID##`

### Workflow
1. Visit http://46.101.179.93 and see `{ message: "Hello Docker World" }`
2. Start dev server: `yarn dev`
3. Make changes and verify it's working
4. Push changes to `master`
  4. Docker Hub should detect the new code and build a new image: https://hub.docker.com/repository/docker/potgied/docker_express/builds
5. If the build is a success then [Watchtower](https://github.com/containrrr/watchtower) on the server will check for changes and deploy the new container. After a few minutes you should see your changes on http://46.101.179.93
