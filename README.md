# docker-build


1. To build a docker container, first choose a template from the existing builds in this repo.

2. Then edit your conda.yml and or Dockerfile to add the programs you needs.

3. Then build the container (don't forget the `.`):

`docker build -t my-image .`

4. Test your container 

`docker run -it my-image bash`

5. Push your working repo to dockerhub