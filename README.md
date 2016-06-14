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

## Configuration:

There isn't much to set up. In the `.openshift/action_hooks/deploy` file, there are 2 booleans at the top of the file. You probably want `YII_INIT` to stay true, but you can stop it from running init if you want. `YII_MIGRATE` is set to `false` by default. This is because by default, on a fresh setup, you probably wouldn't have a database to migrate into anyways. Also, if you did, you could accidently migrate junk into it and mess it up. So you manually have to set `YII_MIGRATE` to `true` when you are ready to migrate. From then on out, it probably can be left as `true`.

**This does not set up your database for OpenShift!** You still need to edit your Yii app and place in the OpenShift environment variables for the database information. That is beyond the scope of this project. This is just to help you get your stock Yii2 app running on an OpenShift cartridge. A Yii2 basic app, OpenShift sets the DocumentRoot to `/web`. However, a Yii2 Advanced App, OpenShift sets the DocumentRoot to `/` because it can't figure it out. We create Symlinks to handle setting the DocumentRoot and accessing the `backend` section. This also handles the `init` for a Yii2 Advanced App, and handles Composer for your app. Composer is set for production, so it **DOES NOT INCLUDE** the `require-dev` dependencies.

With a Yii2 Advanced App, the DocumentRoot of your site will be the `frontend/web` directory. We create a symlink in the root of the site and name it `web` linked to `/frontend/web`. This satisfies OpenShift so it uses the `web` symlink for your DocumentRoot. We also create a symlink in the frontend's web directory, named `admin`. `/frontend/web/admin` points to `/backend/web`.

To access the backend, just add `/admin` to your URL, just like traditional member systems.

**Examples:**

Frontend: `http://yourapp-name.rhcloud.com`

Backend:  `http://yourapp-name.rhcloud.com/admin`


## PLEASE NOTE:

These are rough instructions. I will update this README soon with better instructions. I simply want to use cURL to download the GitHub repo and unzip only the `.openshift` directory. Basically you could cd with terminal into your project's root and copy/paste a command and it will put the `.openshift` directory right where it belongs. The only need to clone this repo, would be if you wanted to contribute to the project, or for your own record. I whiped this up, and it will probably be tweaked in the future.

I lost this and spent forever digging through my backups to find it. So I wanted it somewhere I could always find it :)

If you use Yii2 and OpenShift, I hope this helps you!

## TODO:

 - Fix cURL command to just pluck out `.openshift` directory in current project.

 - Allow control over backend (admin) symlink

 - Create video tutorial

 - Revise README
