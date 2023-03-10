# Start from the official Python base image.

FROM python:3.9

# Set the current working directory to /code.

# This is where we'll put the requirements.txt file and the app directory.


WORKDIR /code

# Copy the file with the requirements to the /code directory.

# Copy only the file with the requirements first, not the rest of the code.

# As this file doesn't change often, Docker will detect it and use the cache for this step, enabling the cache for the next step too.


COPY ./requirements.txt /code/requirements.txt

# Install the package dependencies in the requirements file.


RUN pip install --no-cache-dir --upgrade -r /code/requirements.txt

# Copy the ./app directory inside the /code directory.


COPY ./app /code/app

# Set the command to run the uvicorn server.

EXPOSE 8000

# CMD ["uvicorn", "app.main:app", "--proxy-headers" , "--host", "127.0.0.1", "--port", "8001"]

# CMD ["uvicorn", "app.main:app", "--reload" , "--host", "127.0.0.1", "--port", "8000"]

CMD ["python", "./app/main.py"]
