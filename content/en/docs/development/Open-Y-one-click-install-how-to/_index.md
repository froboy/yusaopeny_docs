---
title: one-click install how-to
aliases:
  - /docs/wiki/open-y-one-click-install-how-to/
---

This walk-through is outdated and is in the process of being updated. Instead, try:

- A [video walk-through of installing YMCA Website Services for tech novices](https://www.youtube.com/watch?v=nGyMJCwMsqM)
- An overview of the [YMCA Website Services Sandboxes]({{< relref "Sandboxes" >}})

### Installing YMCA Website Services on DigitalOcean droplet

1. Create Ubuntu 16.04 LTS x64 droplet in area close to your location
![image](https://user-images.githubusercontent.com/563412/44273919-6ffd8c80-a249-11e8-958b-3d7fbee6108d.png)

Use 2Gb droplet or more powerful if you need. Do not use 1Gb option - YMCA Website Services will fail on it.

2. Login to the SSH console of the droplet
3. Follow the comment from https://github.com/YCloudYUSA/yusaopeny-project/blob/8.1.x/scripts/openyonclickinstall.sh
Basically - run a command under root
```sh
curl -Ls http://bit.ly/initopeny | bash -s
```
The command above will run approximately 10 minutes.
4. In the end you should see a message similar to
```
Open http://127.0.0.1/core/install.php to proceed with OpenY installation.
```
5. Open the link from the above message(from your console, not from this document) with your browser and proceed with YMCA Website Services installation.

Enjoy.

---

In order to install the latest beta release of YMCA Website Services 2.0 change the command on step 3:

```sh
curl -Ls http://bit.ly/initopeny | bash -s beta
```

---

If you find any issues please post a message to the issue queue https://github.com/YCloudYUSA/yusaopeny/issues
