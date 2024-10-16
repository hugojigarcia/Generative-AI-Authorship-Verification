# NLP

python -m venv venv
venv\Scripts\activate

python.exe -m pip install --upgrade pip
pip install -r requirements.txt

pip install pip-tools==7.4.1
pip-compile requirements.in
