# Lilypad DeepScaleR 1.5B

Run [DeepScaleR 1.5B](https://ollama.com/library/deepscaler) on Lilypad Network.

## Getting Started

```bash
lilypad run github.com/Lilypad-Tech/lilypad-deepscaler:6a8675a15f56b0792ada4646a6df5a49867929e9 \
-i request="$(echo -n '{
  "model": "deepscaler:1.5b",
  "messages": [{
    "role": "system",
    "content": "you are a helpful AI assistant"
  },
  {
  "role": "user",
  "content": "what is the animal order of the frog?"
  }],
  "stream": false,
  "options": {
    "temperature": 1.0
  }
}' | base64 -w 0)"
```

## Available Scripts

In the project directory, you can run:

### [`scripts/configure`](scripts/configure)

Configure your module.
Set the following values in the [`.env` file](.env)

```
MODEL_NAME
MODEL_VERSION
DOCKER_HUB_USERNAME
DOCKER_IMAGE
GITHUB_REPO
```

### [`scripts/build [--major] [--minor] [--patch] [--local]`](scripts/build)

Builds the Docker image and pushes it to Docker Hub.

### `--major`, `--minor`, and `--patch` Flags

Increment the specified version before building the Docker image.

#### `--local` Flag

Loads the built Docker image into the local Docker daemon.

### [`scripts/run`](scripts/run)

Run your module.

## Learn More

To learn more about Lilypad, check out the [Lilypad documentation](https://docs.lilypad.tech/lilypad).
