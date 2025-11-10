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

## BackEnd: scenario curl testing
### change lat, lon, and scenario names for checking. Examples below

```bash
curl -s -X POST http://127.0.0.1:8000/api/calculate_lri \
    -H "Content-Type: application/json" \
    -d '{"lat":37.5,"lon":127.0,"scenario":"severe"}'

curl -s -X POST http://127.0.0.1:8000/api/calculate_lri \
    -H "Content-Type: application/json" \
    -d '{"lat":37.5,"lon":127.0,"scenario":"warning"}'

curl -s -X POST http://127.0.0.1:8000/api/calculate_lri \
    -H "Content-Type: application/json" \
    -d '{"lat":37.5,"lon":127.0,"scenario":"hard_stop"}'

curl -s -X POST http://127.0.0.1:8000/api/calculate_lri \
    -H "Content-Type: application/json" \
    -d '{"lat":37.5,"lon":127.0,"scenario":"very_good"}'
```
