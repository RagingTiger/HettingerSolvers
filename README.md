# About
Repository of [JupyterLab](https://jupyter.org/) notebooks to explore the
**solvers** presented in
[Raymond Hettinger's](https://twitter.com/raymondh) talk:
[Modern solvers: Problems well-defined are problems solved - PyCon2019](https://youtu.be/_GP9OpZPUYc).
Please see https://github.com/rhettinger/rhettinger.github.io for original
slides/website source code.

# Jupyter
Below are the *instructions* for running the **JupyterLab** notebook.

## Development
To deploy a simple *single user* environment (i.e. for *development*) simply
run the following *Docker* commands (**note**: this assumes you are already
in the `Modern-Solvers-PyCon2019` directory):
```
docker run -d \
           --rm \
           --name hettsolver.dev \
           -e JUPYTER_ENABLE_LAB=yes \
           -p 8888:8888 \
           -v $PWD:/home/jovyan \
           jupyter/scipy-notebook:lab-3.4.4 && \
sleep 5 && \
docker logs hettsolver.dev 2>&1 | grep "http://127.0.0.1" | tail -n 1 | awk '{print $2}'
```
Click the link (should look similar to:
http://127.0.0.1:8888/lab?token=LONG_ALPHANUMERIC_STRING) which will
`automatically` log you in and allow you to start running the *notebooks*.
