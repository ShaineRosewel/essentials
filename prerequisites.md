export PIPENV_VENV_IN_PROJECT=1  
pipenv --python 3.7  
pipenv shell  
pipenv install sklearn==0.0  
pipenv install ipykernel  


export PIPENV_VENV_IN_PROJECT=1 && pipenv --python 3.10 && pipenv shell && pipenv install ipykernel && source .venv/bin/activate && python -m ipykernel install --user --name=$(basename $VIRTUAL_ENV) --display-name "Python 3.10 (Pipenv)"


# Using Dev Containers

- Command + Shift + p
- Build w/o cache if it errors on build only
