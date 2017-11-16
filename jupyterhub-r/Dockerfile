# Run it with docker run -d -p 8000:8000 --env-file=environment_file melvinodsa/jupyterhub-r
# visit github.com/melvinodsa/docker-stacks for the docker files
FROM melvinodsa/jupyterhub

LABEL maintainer="Melvin Davis <melvinodsa@gmail.com>"

# R pre-requisites
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    fonts-dejavu \
    gfortran \
    gcc && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# R packages
RUN conda install --quiet --yes \
    'r' \
    'r-essentials' && \
    conda clean -tipsy
