FROM python:alpine3.19

WORKDIR /app

COPY requirements.txt .

RUN python -V
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD [ "python", "/app/main.py" ]
—----------------------------------------------------------------------------------------------------------------------------
requirements.txt
—----------------------------------------------------------------------------------------------------------------------------
certifi==2023.11.17
charset-normalizer==3.3.2
idna==3.6
requests==2.31.0
urllib3==2.1.0

—----------------------------------------------------------------------------------------------------------------------------
action.yml
—----------------------------------------------------------------------------------------------------------------------------
name: Ping URL
description: Ping URL until maximum trials have exceeded. If result is not 200 until then, fails the action.

inputs:
  url: # INPUT_URL
    description: URL to ping.
    required: true
  max_trials: # INPUT_MAX-TRIALS
    description: Maximum number of trials until action fails.
    default: '10'
    required: false
  delay:
    description: Delay in seconds between trials.
    default: '5'
    required: false

runs:
  using: docker
  image: Dockerfile

