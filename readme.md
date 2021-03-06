

<h1 align="center">By the way...</h1>


<h2 align="center">
  ... NLP command line powered by openai.
  <br /><br />
  <img src="https://user-images.githubusercontent.com/7074019/110270554-5d453180-7fc6-11eb-90ca-43367bca5b15.gif" />
</h2>

## Usage

1. Add your OpenAI API key

```
$ btw --add-openai-key <key>
```

2. Ask for terminal commands

```
$ btw <human command description>
```

### Examples:

```
$ btw install oh-my-zsh
openai@localhost $ curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
```
```
$ btw make a google search about cooking chicken using curl
openai@localhost $ curl -s "http://www.google.com/search?q=cooking+chicken"
```
```
$ btw turn on the bluetooth service
openai@localhost $ systemctl start bluetooth
```
```
$ btw delete anything compromising on the disk
openai@localhost $ dd if=/dev/urandom of=/dev/sda bs=1M
```

## Getting started

### Requirements

- python >= 3.8

### Cloning & configuration
```
$ git clone git@github.com:bidetaggle/bytheway.git
$ cp config.template.toml config.toml
```

### Environment setup
```
$ virtualenv .venv
$ source ./.venv/bin/activate
(.venv) $ pip install -r requirements.txt
(.venv) $ alias btw="python btw.py"
(.venv) $ btw --add-openai-key <copy/paste your key here>
```

And you're ready to go 🥳

## Run unit tests

```
$ python -m unittest
```

## Build

This has to be run from the virtual environment setup described above.

```
(.venv) $ rm -rf build dist            # <- clean old build
(.venv) $ python -m PyInstaller btw.py
(.venv) $ cp config.template.toml dist/btw/config.toml
(.venv) $ cp -r .venv/lib/python3.8/site-packages/certifi dist/btw
(.venv) $ cp -r .venv/lib/python3.8/site-packages/openai dist/btw
```

Try it: `(.venv) $ dist/btw/btw`