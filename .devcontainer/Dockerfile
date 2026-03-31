FROM python:3.12-slim

RUN apt-get update && apt-get install -y \
	curl \
	git \
	git-lfs \
	&& rm -rf /var/lib/apt/lists/*


RUN git lfs install --system
RUN curl -LsSf https://astral.sh/uv/install.sh | sh

ENV PATH="/root/.local/bin:$PATH"

WORKDIR /app

RUN uv venv .Andr3sss

COPY requirements.txt .

RUN uv pip install --python .Andr3sss/bin/python -r requirements.txt

ENV VIRTUAL_ENV=/app/.Andr3sss
ENV PATH="/app/.Andr3sss/bin:$PATH"