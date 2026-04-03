My first DevOps + AI playground
# DevOps Playground – Flask Service

A minimal Flask service for a DevOps playground project.

## Endpoints

| Method | Path      | Response                  |
|--------|-----------|---------------------------|
| GET    | `/`       | `Hello DevOps`            |
| GET    | `/health` | `{"status": "ok"}`        |

## Run locally

```bash
pip install -r requirements.txt
python app.py
```

Service will be available at `http://localhost:5000`.

## Run with Docker

```dockerfile
FROM python:3.13-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY app.py .
EXPOSE 5000
CMD ["python", "app.py"]
```

```bash
docker build -t devops-playground .
docker run -p 5000:5000 devops-playground
```
