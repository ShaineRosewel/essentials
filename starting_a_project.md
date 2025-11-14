I usually find it easy to forget how to set up my working environment especially when I aim to work on a Jupyter Notebook in Visual Studio Code. Hence, I put here the steps.
Terminal commands: 
  1. `pipenv install`
  2. `pipenv shell`
  3. `pipenv install ipykernel`
  4. `pipenv run python -m ipykernel install --user --name=your-environment-name --display-name="your-environment-display-name"`

On your Jupyter Notebook
  1. Command + Shift + P: Select "Developer: Reload Window"
  2. On the upper right corner, click on "Select Kernel" button
  3. Select "Jupyter Kernel" when asked to choose a kernel source.
  4. Your set "your-environment-display-name" should appear for you to select.

