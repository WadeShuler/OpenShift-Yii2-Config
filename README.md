# OpenShift-Yii2-Config
An OpenShift config for Yii2 (Basic &amp; Advanced). OpenShift isn't compatible with the Yii2 Advanced app due to the frontend and backend. This config will get you running quick and easy!

## How To Download

### Option 1:
You could clone this repo just like normal. Then copy the `.openshift` directory into your Yii2 app's root directory.

**DO NOT** clone this into your current project, in the same directory where you already have a `.git` directory! I do not know what that would do, but we don't want to mess up your current project's git repo!

### Option 2:

Use cURL to download the zip of this archive (without the `.git` directory).

    curl -LOk https://github.com/WadeShuler/OpenShift-Yii2-Config/archive/master.zip
    unzip master.zip -d ./OpenShift-Yii2-Config

You will then still need to copy the `.openshift` directory out of the `OpenShift-Yii2-Config` directory and into the root of your Yii2 app's project.

*#PLEASE NOTE:#*

These are rough instructions. I will update this README soon with better instructions. I simply want to use cURL to download the GitHub repo and unzip only the `.openshift` directory. Basically you could cd with terminal into your project's root and copy/paste a command and it will put the `.openshift` directory right where it belongs. The only need to clone this repo, would be if you wanted to contribute to the project, or for your own record. I whiped this up, and it will probably be tweaked in the future.

I lost this and spent forever digging through my backups to find it. So I wanted it somewhere I could always find it :)

If you use Yii2 and OpenShift, I hope this helps you!
