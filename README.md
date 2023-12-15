# SDU SSO login

现在已经能
Current features:

- login to SDU SSO, and bind fake device fingerprint to the account to bypass the 2FA process
- get user info
- get lessons from bkzhjx.wh.sdu.edu.cn
- get classroom info from pcms.sdu.edu.cn (TO be enhanced and stored in database and support all API features, not yet finished)

## Install

```bash
pdm install
```

or use pip to install:

```bash
pip install -r requirements.txt
```

## Usage

First, it is recommended that the fingerprint json file be edited. You may use a random json whose keys and values are random strings. I am not sure whether a too-simple string can pass the device fingerprint check on SDU pass.

```bash
python ./src/main.py  # get user info
python ./src/bkzhjx_login.py  # get lessons
```

## Some findings

In cookies file we can find a `SERVERID`. Perhaps we can try getting data from all servers at the same time when some of the servers' response is terribly slow.
