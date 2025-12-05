Install pymilvus (Python client for Milvus)

1) Create & activate a virtual environment
- Linux/macOS:
  python3 -m venv .venv && source .venv/bin/activate
- Windows (PowerShell):
  python -m venv .venv; .\.venv\Scripts\Activate.ps1

2) Upgrade packaging tools
python -m pip install -U pip setuptools wheel

3) Install pymilvus
python -m pip install -U pymilvus

4) Verify installation
python -c "import pymilvus; print(pymilvus.__version__)"

Notes
- pymilvus is a client library only — you must run a Milvus server separately to use it.
- Easiest server option: run Milvus in Docker (requires Docker). Example:
  docker run -d --name milvus-standalone -p 19530:19530 -p 19121:19121 milvusdb/milvus:latest
- If you cannot use Docker on your machine, consider a cloud dev environment (Codespaces, Gitpod) or a small VM.
- If installation fails on grpcio builds, first ensure pip/setuptools/wheel are up-to-date and install platform build tools (Xcode command line tools on macOS, build-essential & Python dev headers on Linux, Visual C++ Build Tools on Windows). For macOS on Apple Silicon, ensure updated pip and Xcode tools.
- To match a specific Milvus server version, pin the client version, e.g. python -m pip install "pymilvus==2.2.0"