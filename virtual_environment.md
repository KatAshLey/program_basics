# use git bash within folder run each of these lines. creates a virtual environment
python3 -m venv env  #creates folder
source ./env/Scripts/activate  #activate virtual environment
pip install sqlmodel fastapi[all]

# activate env first in bash source ./env/Scripts/activate

# force the right interpreter in the change interpreter >> env >> script >> python.exe   make sure it says python 3.12.0('env':venv)