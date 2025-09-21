# Jupyter Notebook - Dockerized

Simple installation docker-compose files for C and Python kernel jupyter notebook.

## Set up

These docker compose is set to restart **always** so that whenever you restart your PC they will never be down.

Follow these easy steps to have them up and running quickly:
1. Install [docker engine](https://docs.docker.com/engine/) in your machine (or [Docker Desktop](https://docs.docker.com/desktop/))
2. Navigate to the folder where the docker-compose files are.
3. [Optional] Edit the docker-compose.yaml changing your ```JUPYTER_TOKEN=password```
3. Run ```docker compose up -d ```
4. You can now navigate to http://localhost:8888 to use it via web.
5. Use the JUPYTER_TOKEN you previously set to login via token password.

### Visual Studio Code installation

You can set up the kernel server via VS Code so that you can then work directly in your IDE with jupyter files.

1. Install the [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) VSCode plugin
2. Open any .ipynb file and try to run a code block.
3. VSCode will ask you for what jupyter server to use, select "Existing Jupyter Server"
4. type http://localhost:8888, press enter and type the JUPYTER_TOKEN value you set previously
5. select C kernel if you are working with a C notebook, python3 if otherwise (you can change this at the top right when you have a notebook open)

Done! You saved yourself dirtying your host machine with useless crap :D