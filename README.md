# CraftBuddy

Copyright (C) 2025 Jacob Farnsworth

Have you ever played a game with some kind of crafting system? Have you ever found yourself struggling to plan your crafting goals in such a game? Maybe you've wondered, "How much stone do I need to make 1000 slabs?" or "How many sticks and ingots do I need to make 4 pickaxes?"

CraftBuddy is a web app that can help with a variety of crafting and resource management-related math. CraftBuddy can help with all kinds of queries related to crafting in your favorite games, and more!

This repository contains an environment and docker compose script for deploying the entire CraftBuddy app. The docker compose script deploys containers for the frontend, backend, and a reverse proxy nginx instance. The nginx reverse proxy passes API requests (addresses starting with `/api`) to the backend server, while any other requests are passed to the frontend.

The CraftBuddy project consists of the following repositories:
* [craftbuddy-frontend](https://github.com/JFarNTIG/craftbuddy-frontend), frontend server built with React + Vite.
* [craftbuddy-backend](https://github.com/JFarNTIG/craftbuddy-backend), backend API server built with Flask.
* [craftbuddy](https://github.com/JFarNTIG/craftbuddy), environment and docker compose script for deploying the CraftBuddy app

CraftBuddy also depends on [crafterlib](https://github.com/JFarNTIG/crafterlib), a Python library that provides game item and recipe data and has a variety of functions for crafting-related math.

## Getting Started

If you want to deploy a development environment for the frontend or backend service individually, then check the respective repository and follow the instructions there. See the above section for links.

Otherwise, follow the instructions below to deploy the CraftBuddy app with all services together:

Clone the repository, making sure to also clone submodules:
```
git clone --recurse-submodules https://github.com/JFarNTIG/craftbuddy && cd craftbuddy
```

Run the docker compose script:
```
docker compose up
```

To run as a daemon (detached from the terminal) you can add the `-d` flag:
```
docker compose up -d
```

To rebuild images (for example, if changes were made within the submodules) you can add the `--build` flag:
```
docker compose up --build
```

After starting the container group, the CraftBuddy app is available on port 80:
```
http://localhost/
```

## Resources

* [Docker documentation](https://docs.docker.com/)
* [Compose documentation](https://docs.docker.com/compose/)
* [nginx documentation](https://nginx.org/en/docs/)

## License

CraftBuddy is licensed under the terms of the GNU General Public License, version 2. See the file `LICENSE` for the full license text.