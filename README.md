# payphone-club.github.io

Our website.

Located at https://payphone.club

## Running Locally

Install the prerequisites:

```
sudo apt-get update
sudo apt-get install python3 python3-pip
pip install mkdocs mkdocs-image-captions
```

Clone the repo and change to the directory:

```
git clone https://github.com/payphone-club/payphone-club.github.io.git
cd payphone-club.github.io/
```

Serve the site locally:

```
mkdocs serve
```

OR serve the site locally and bind to all network interfaces:

```
mkdocs serve --dev-addr=0.0.0.0:8000
```
