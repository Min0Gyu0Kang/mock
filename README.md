# install python if missing
sudo apt update
sudo apt install -y python3 python3-venv python3-pip

# create and activate venv
python3 -m venv .venv
source .venv/bin/activate

# install python deps
python -m pip install --upgrade pip
pip install -r requirements.txt

# install node dev deps
npm install

# run backend only
npm run backend

# or run both frontend + backend
npm run dev