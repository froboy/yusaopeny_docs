### Welcome to Open Y wiki

### Installing Open Y on DigitalOcean droplet

1. Create Ubuntu 16.04 LTS x64 droplet in area close to your location
![image](https://user-images.githubusercontent.com/563412/44273919-6ffd8c80-a249-11e8-958b-3d7fbee6108d.png)

Use 2Gb droplet or more powerful if you need. Do not use 1Gb option - Open Y will fail on it.

2. Login to the SSH console of the droplet
3. Follow the comment from https://github.com/ymcatwincities/openy-project/blob/8.1.x/scripts/openyonclickinstall.sh
Basically - run a command under root
```sh
bash < <(curl -Ls http://bit.ly/initopeny)
```
The command above will run approximately 10 minutes.

4. In the end you should see a message similar to
```
Open http://127.0.0.1/core/install.php to proceed with OpenY installation.
```
5. Open the link from the above message(from your console, not from this document) with your browser and proceed with Open Y installation.

Enjoy.

If you found any issues - please post a message to issue queue https://github.com/ymcatwincities/openy/issues