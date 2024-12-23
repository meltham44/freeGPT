<img src="https://repository-images.githubusercontent.com/636250478/f62a1186-b84b-4e7a-86f1-145e32163a59" align="right" width=170>

# A freeGPT fork

freeGPT provides free access to text and image generation models. This fork aims to continue and improve the original and currently archived [project](https://github.com/Ruu3f/freeGPT).

## Getting Started:

Uninstall any current versions of freeGPT:

    pip uninstall freegpt

Clone:

    git clone https://github.com/meltham44/freeGPT
    cd freeGPT

Install:

    pip install -e .

## Sources:

This fork aims to use the sources of the original project, because they are free and simple to use, when they work.

| Model        | Website                                                |
| ------------ | ------------------------------------------------------ |
| gpt3         | [chat9.yqcloud.top](https://chat9.yqcloud.top/)        |
| gpt4         | [you.com](https://you.com/)                            |
| gpt3_5       | [vitalentum.net](https://vitalentum.net/free-chat-gpt) |
| prodia       | [prodia.com](https://prodia.com/)                      |
| pollinations | [pollinations.ai](https://pollinations.ai/)            |

Only GPT3.5 works at the moment. GPT3 does work in theory but chat9 has started to use IP blocking, which kicks in quickly.

## Examples:

### Text Completion:

```python
from freeGPT import Client

while True:
    prompt = input("👦: ")
    try:
        resp = Client.create_completion("MODEL", prompt, "SYSTEM_PROMPT")
        print(f"🤖: {resp}")
    except Exception as e:
        print(f"🤖: {e}")
```
`SYSTEM_PROMPT` is optional. It is a string which allows you to specify the model's behaviour. It is only supported by GPT3.5 at the moment.
### Image Generation:

```python
from freeGPT import Client
from PIL import Image
from io import BytesIO

while True:
    prompt = input("👦: ")
    try:
        resp = Client.create_generation("MODEL", prompt)
        Image.open(BytesIO(resp)).show()
        print(f"🤖: Image shown.")
    except Exception as e:
        print(f"🤖: {e}")
```
No work has been put into image generation as of yet.
## Check out the original project:

[![PyPI](https://img.shields.io/pypi/v/freeGPT)](https://pypi.org/project/freeGPT)
[![Downloads](https://static.pepy.tech/badge/freeGPT)](https://pypi.org/project/freeGPT)
[![Status](https://img.shields.io/pypi/status/freeGPT)](https://pypi.org/project/freeGPT)

 - [GitHub](https://github.com/Ruu3f/freeGPT)
 - [PyPi](https://pypi.org/project/freeGPT/)
