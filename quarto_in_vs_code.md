It turns out that quarto render in VS Code, by default, does not seem to use the python version that I have in my pipenv shell. 

# Things I tried and I am not sure which solved the issue but it got solved! 😅

1. In my root folder I added `_environment.local` and inside I defined `QUARTO_PYTHON=/Users/shainerosewelmatala/.local/share/virtualenvs/campaign-optimizer-api-T94xA3Mx/bin/python`
2. On the command line, I ran `export QUARTO_PYTHON=/Users/shainerosewelmatala/.local/share/virtualenvs/campaign-optimizer-api-T94xA3Mx/bin/python` then `quarto render my_qmd.qmd`
3. On the `.qmd` that I am running, I added a YAML key=value `jupyter: campaign-optimizer-api-environment`

# Now I'm sure

1. `jupyter kernelspec list --json` to check which python is being used by the enviroment i am using. Take note of it and use to define `QUARTO_PYTHON` and `jupyter:` in YAML.
2. On the `.qmd` that I am running, I added a YAML key=value `jupyter: campaign-optimizer-api-environment`
3. On the command line, I ran `export QUARTO_PYTHON=/Users/shainerosewelmatala/.local/share/virtualenvs/campaign-optimizer-api-T94xA3Mx/bin/python` then `quarto render my_qmd.qmd` and it worked!!!
