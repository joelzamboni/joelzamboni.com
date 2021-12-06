# Personal Website
This is my personal website

### Local Development with Hot Reload
```
python3 -m venv .venv
pip install -r .requirements.txt
source .venv/bin/activate
uvicorn main:app --reload
```

### Simple test
```
docker build . -t app && docker run -p 127.0.0.1:8000:8000/tcp -it app
```
