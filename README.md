# docker-sentiment [![Travis](https://img.shields.io/travis/anroots/docker-sentiment.svg)](https://travis-ci.org/anroots/docker-sentiment) [![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://github.com/anroots/docker-sentiment/blob/master/LICENSE.md) [![Docker Pulls](https://img.shields.io/docker/pulls/anroots/sentiment.svg)](https://hub.docker.com/r/anroots/sentiment)

Docker container for the [Node.js sentiment library](https://github.com/thisandagain/sentiment) for analysing positive/negative affect in a string of text.

The container runs a HTTP server that accepts POST requests and responds with analysis results.

## Requirements

* Docker

## Install

Run the container and publish port `8888`.

```
$ docker run -p 8888:8888 anroots/sentiment
```

## Usage

Send a HTTP POST request to the Docker container IP, port 8888. The text to be analysed must be sent in the `text` key.

```bash
curl --data "text=I%20am%20happy" http://localhost:8888 
{"score":3,"comparative":1,"tokens":["i","am","happy"],"words":["happy"],"positive":["happy"],"negative":[]}
```

## License

The [Sentiment library](https://github.com/thisandagain/sentiment) is developed and licensed by [@thisandagain](https://github.com/thisandagain).
The Docker server in this repository is licensed under MIT.