## Installed
- python
- uv
- git
- docker cli
    - after install - check using - `docker version`  - it should show both client and server
    - if you see both then we are good
- docker-compose - we also needthat
    - test using `docker compose`
    - when we install apps like fast API with model and application - which is connecting to model
        - and how you setup an env with that or how you create DEV containers with it - thats where we need docker compose
        - you can use it launched using Docker Compose

- MLFlow
    - open source tool 
    - mlflow.org
    - for model tracking - to be used on experimentation, model training, tracking , comparing model algorithm performance
    - To setup
        - go to /deployment/mlflow folder
        - then run `docker compose -f docker-compose.yaml up -d`
        - validate setup by running `docker compose ps`
        - you can also open the mflow app in the browser by clicking the URL for the port 5555 (in this ex it was https://improved-space-halibut-pwwqqq5xg4crggj-5555.app.github.dev/#/prompts)
        
- Extensions
    - python
    - jupyter
    - docker extension
- other
    - docker hub account at hub.docker.com
        - we need this to publish our model package  - to share with dev and data scientist for distribution
        - if using for business - use podman - when you have to use podman - you have to install docker compose
        
    