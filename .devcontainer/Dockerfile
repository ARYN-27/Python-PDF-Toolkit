# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.202.5/containers/python-3/.devcontainer/base.Dockerfile

# [Choice] Python version (use -bullseye variants on local arm64/Apple Silicon): 3, 3.10, 3.9, 3.8, 3.7, 3.6, 3-bullseye, 3.10-bullseye, 3.9-bullseye, 3.8-bullseye, 3.7-bullseye, 3.6-bullseye, 3-buster, 3.10-buster, 3.9-buster, 3.8-buster, 3.7-buster, 3.6-buster
ARG VARIANT="3.10-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

# [Choice] Node.js version: none, lts/*, 16, 14, 12, 10
ARG NODE_VERSION="none"
RUN if [ "${NODE_VERSION}" != "none" ]; then su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi

# [Optional] If your pip requirements rarely change, uncomment this section to add them to the image.
# COPY requirements.txt /tmp/pip-tmp/
# RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
#    && rm -rf /tmp/pip-tmp

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1


RUN sudo apt update && sudo apt-get upgrade -y 
RUN /usr/local/bin/python -m pip install -U ipykernel
RUN /usr/local/bin/python -m pip install --upgrade pip

####################################################################
#installing python3-venv
#RUN apt install -y python3-venv

# For python env creation - env name => genesis

#WORKDIR /workspaces/Code/genesis
#RUN python3 -m venv dev_env
#ENV virtualenv /dev_env
#ENV PATH="/workspaces/Code/dev_env/bin:$PATH"
#RUN source /workspaces/Code/dev_env/bin/activate

#ENV Activation 
#COPY entrypoint.sh /entrypoint.sh
#RUN chmod +x /entrypoint.sh
#ENTRYPOINT ["/entrypoint.sh"]
#RUN source dev_env/bin/activate
####################################################################


# Requirements install
WORKDIR /workspaces/Code
COPY requirements.txt /tmp/requirements.txt
RUN python3 -m pip install -r /tmp/requirements.txt

#Welcome to GENESIS App Container
#RUN echo "Welcome to GENESIS App Container"
#CMD ["echo "Welcome to GENESIS App Container""]







