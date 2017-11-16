# Designed to be run as 
# 
# docker run -it -p 8000:8000 --env-file=env_file melvinodsa/jupyterhub 

FROM jupyterhub/jupyterhub

MAINTAINER Melvin Davis <melvinodsa@gmail.com>

# Install oauthenticator from git
RUN python3 -m pip install oauthenticator

# Create oauthenticator directory and put necessary files in it
RUN mkdir /srv/oauthenticator
WORKDIR /srv/oauthenticator
ENV OAUTHENTICATOR_DIR /srv/oauthenticator
ADD jupyterhub_config.py jupyterhub_config.py
ADD addusers.sh /srv/oauthenticator/addusers.sh
ADD userlist /srv/oauthenticator/userlist
ADD ssl /srv/oauthenticator/ssl
RUN chmod 700 /srv/oauthenticator
RUN conda install -y notebook

RUN ["sh", "/srv/oauthenticator/addusers.sh"]
