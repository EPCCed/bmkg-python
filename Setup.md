# Initial set up of virtual environment

```bash
module load cray-python
WORK=${HOME/home/work}
cd $WORK
python -m venv --system-site-packages jupyter
source jupyter/bin/activate

pip install jupyter-lab
```
# Subsequent use
```bash
module load cray-python
WORK=${HOME/home/work}
source $WORK/jupyter/bin/activate
```

# Getting materials
```bash
cd $WORK
git clone https://github.com/EPCCed/bmkg-python.git
cd bmkg-python
```
# Running notebook server
```bash
export JUPYTER_RUNTIME_DIR=$PWD
jupyter-lab --ip=0.0.0.0 --no-browser
```

Take note of login node, port and token

Line like: http://127.0.0.1:8888/lab?token=d4c7cfebe7bfd1eb9d37e2149

On your local machine run
```bash
ssh USERNAME@login$NODENUMBER.archer2.ac.uk -L$PORT:localhost:$PORT
```

On your browser go to `localhost:PORT/lab?token=TOKEN`
