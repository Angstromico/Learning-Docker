# Python Random Number Generator - Docker App

A simple Python application that generates random numbers within a user-specified range, packaged as a Docker container.

## Overview

This interactive Python script prompts users to enter a minimum and maximum number, then generates a random number within that range. The application is designed to run in an interactive Docker container.

## Docker Setup

### Building the Image

```bash
docker build -t my-app-py .
```

### Running the Application

**IMPORTANT**: This application requires interactive mode to function properly. Use the `-it` flag to enable interactive terminal access.

```bash
docker run -it my-app-py
```

The `-it` flag is essential because:
- `-i` (interactive) keeps STDIN open for user input
- `-t` (tty) allocates a pseudo-terminal for proper interaction

### Alternative: Running in Detached Mode with Terminal Access

If you prefer to run the container in the background while maintaining interactive capabilities:

```bash
docker run -dit my-app-py
docker attach <container_id>
```

## Usage Example

When you run the container with `docker run -it my-app-py`, you'll see:

```
Please enter the min number: 1
Please enter the max number: 100
42
```

## Application Logic

The Python script (`rng.py`) performs the following steps:
1. Prompts user for minimum number
2. Prompts user for maximum number  
3. Validates that max >= min
4. Generates and displays a random number in the specified range

## Error Handling

If the maximum number is less than the minimum number, the application will display:
```
Invalid input - shutting down...
```

## File Structure

- `Dockerfile` - Docker configuration
- `rng.py` - Python random number generator script
- `README.md` - This documentation

## Requirements

- Docker installed on your system
- No additional Python dependencies required (uses built-in `random` module)
