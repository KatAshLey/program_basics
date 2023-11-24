# creates a virtual environment
# use git bash. Ensure you are in the correct folder. Run first 3 lines one after another

# creates folder
python3 -m venv env  

# activate virtual environment
source ./env/Scripts/activate  

# install sqlmodel and fastapi into new environment
pip install sqlmodel fastapi[all]




# activate virtual environment that has been created.  
source ./env/Scripts/activate

# force the right interpreter in the environment
# make sure it says python 3.12.0('env':venv) in bottom right of screen
ctrl + shift + p
python select interpreter >> enter interpreter path >> find >> env >> script >> python.exe   