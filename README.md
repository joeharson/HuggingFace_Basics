# Hugging Face Base

Download and run Hugging Face models locally via an interactive terminal chat or a FastAPI endpoint.

---

## 1. Setup

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 2. Choose Your Model

Open `hf_model_download.py` and `fastapi_infrence.py`, then set `model_name` to any Hugging Face repo ID:

```python
model_name = "Qwen/Qwen3-0.6B"  # Replace with any model (e.g., HuggingFaceTB/SmolLM2-135M-Instruct)
```

The model weights will automatically download to the local `model/` directory on first run.

---

## 3. Run

### Interactive CLI Chat
Downloads the model and starts a terminal chat:
```bash
python hf_model_download.py
```
> Type your prompt and press **Enter**. Type `exit` to quit.

### FastAPI Server
Starts the REST API at `http://127.0.0.1:8000`:
```bash
python fastapi_infrence.py
```

Test and check the API in your browser:
- [FastAPI - Swagger UI](http://127.0.0.1:8000/docs)

Or via curl:
```bash
curl "http://127.0.0.1:8000/ask?question=Hello"
```

### Docker
Build and run the container:
```bash
docker build -t hf-base .
docker run -p 8000:8000 -v ${PWD}/model:/app/model hf-base
```

---

## Acknowledgements

Special thanks to AI with Tiru for guidance and collaboration.
