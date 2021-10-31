# utilities

## Python codes for configuring virtual enviroments in jupyter lab
``` pip install jupyter lab
    python -m venv venv
    pip install ipykernel
    pip install -r requirements.txt
    python -m ipykernel install --user --name=venv
    jupyter kernelspec list
    jupyter kernelspec uninstall venv
