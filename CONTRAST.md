
# This README is intended to provide the basic instructions on configuring the Contrast Ruby agent in RailsGoat

## Modifications made to the source project
- contrast_security.yaml file added
- DockerFile updated to install Contrast's Ruby agent (RUN bundle add contrast-agent -v 3.12.1)
  unpin the version for the latest Ruby agent.
- docker-compose.yml updates to configure Contrast Ruby agent's authentication

## Steps

1. Configure Contrast environmental variables
Edit the docker-compose.yml file and update the following API authentication parameters.  
NOTE: If you are unsure of the values please visit our main documentation on this here: https://docs.contrastsecurity.com/en/find-the-agent-keys.html

Authentication:
```
      - CONTRAST__API__URL=https://app.contrastsecurity.com/Contrast
      - CONTRAST__API__API_KEY={agent API KEY}
      - CONTRAST__API__SERVICE_KEY={agent Service key}
      - CONTRAST__API__USER_NAME={agent user name}
      - CONTRAST__APPLICATION__NAME=RailsGoat
      - CONTRAST__SERVER__NAME=DockerRailServer
```
2. Refer to the /README.md's ## Docker Install section to build and deploy the container.