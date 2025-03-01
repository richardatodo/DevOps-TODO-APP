FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
# First install C dependencies needed for thriftpy2
RUN apt-get update && apt-get install -y gcc python3-dev
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "main.py"]
EXPOSE 5000