# Easy YouTube (and more) archival!
> Watch the companion video at: https://www.youtube.com/watch?v=dQw4w9WgXcQ

# Table of Contents
- [Easy YouTube (and more) archival!](#easy-youtube-and-more-archival)
- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [Motivation](#motivation)
- [Installation](#installation)
  - [Dependencies](#dependencies)
  - [Windows](#windows)
    - [1. Download this repo](#1-download-this-repo)
    - [2. Install Chocolatey](#2-install-chocolatey)
    - [3. Install everything else](#3-install-everything-else)
  - [Linux/other *nixes](#linuxother-nixes)
    - [1. Install Dependencies](#1-install-dependencies)
    - [2. Install YouTube-dl](#2-install-youtube-dl)
    - [3. Clone this repo](#3-clone-this-repo)
  - [Mac OS X](#mac-os-x)
- [Usage](#usage)
- [Updating](#updating)

# Introduction
Do you watch YouTube? Do you enjoy watching YouTube? ~~Do you want to be alone forever?~~ Soon you may be in danger of losing your ability to rejoyce in these actions as a result of litigation, such as COPPA and Article 13, or general stupidity, like machine learning and outsourced moderation.

But how can one go about fixing this issue and ensure that they ~~stay alone~~ can continue to enjoy the content they love forever and ever? Easy! Just use this amazing one-step solution to ~~fix your loneliness~~ back-up your favourite content!

# Motivation
~~None.~~

As far as size is concerned, YouTube is kind of massive. Too massive to be truly backed up, being in the neightbourhood of hundreds, and possibly even thouseands of petabytes in size. The [Internet Archive](https://archive.org/index.php), the largest and most comprehensive archive of internet stuff we have is considrably smaller at under a petabyte. (way under a petabyte, in fact)

This means that, chances are, no one will save the content you like, as much as they would love to do so, and thus, the responsibility to preserve this vital piece of internet history falls on each and every one of us.

Annotations are already gone. Let's not let the videos go as well.

# Installation
You will need a stable internet connection. *(gasp)* Also, 
```
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
```

## Dependencies
 - **youtube-dl** is what downloads the videos
 - **python** is what youtube-dl runs on
 - **ffmpeg** is what merges the audio, video, and metadata into a single file
 - **aria2** is a download acceleraotr for the command line
 - **mpv** is the only good video player, and is not required, but very useful anyway
 - **git** makes your life easier, especially on Linux, but also can do so on Windows
 - **curl** is used to download youtube-dl on Linux/OS X
 - **chocolatey** is used to download youtube-dl and its dependencies on Windows

## Windows
> **You will need administrator access.**

### 1. Download this repo
[Download the zip](https://github.com/oofdere/easy-yt-archival/archive/master.zip) and extract it to a reasonable location. (I reccomend a floder in the location you will store your videos)

If you know how to, you may also [use git](#3-clone-this-repo) to do this step. If you do, come back here instead of going on to the Usage section.
```
cd [directory where you want the folder]
git clone -r https://github.com/oofdere/easy-yt-archival
```

### 2. Install Chocolatey
Chocolatey is a package manager, a program that installs other programs for you. Other package managers include Steam or the Microsoft Store, and Chocolatey is no different. It handles the hard stuff for you.

Open a command prompt (poweshell or cmd) as administrator, either by pressing `Win+X` followed by `A` or double-clicking `powershell` in the zip you downloaded.

Run this command to download and install `choco`.
```batch
cmd /c start powershell -noexit -command "Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))"
```
When it completes, `exit` the command prompt.

### 3. Install everything else
Because we installed Chocolatey, the rest of the install is as simple as opeining up another command prompt, by pressing `Win+X` followed by `A` or double-clicking `powershell` in the zip, and then running the following:
```batch
choco install aria2 ffmpeg mpv youtube-dl
```

Move on to the [Usage](#usage) section.


## Linux/other *nixes
> These instructions are written for the apt package manager, used in Debian and Ubuntu, though you should know enough linux to install packages in your distro, I would hope. Most of the time the package names will be the exact same across all distros. Some distros may need an additional package manager for some/all packages.
>
> **You will need superuser/administrator access.**

### 1. Install Dependencies
Make sure your system is up to date before continuing.
```
sudo apt update
sudo apt upgrade
```
Then install the dependencies.
```
sudo apt install aria2 ffmpeg mpv python curl git
```

### 2. Install YouTube-dl
> Check https://ytdl-org.github.io/youtube-dl/download.html for the most up-to-date instructions

YouTube-dl is installed without the package manager as it has a rolling release and package managers can and do lag behind the latest version.
```console
oof@dere:~$ sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
oof@dere:~$ sudo chmod a+rx /usr/local/bin/youtube-dl
```
YouTube-dl is now installed on your system.

### 3. Clone this repo
Either [download the zip](https://github.com/oofdere/easy-yt-archival/archive/master.zip) and extract to a reasonable location (I reccomend a floder in the location you will store your videos) or use git:
```console
oof@dere:~$ cd [directory where you want the folder]
oof@dere:~$ git clone -r https://github.com/oofdere/easy-yt-archival
```

Move on to the [Usage](#usage) section.


## Mac OS X
Follow the [Linux instructions](#linuxother-nixes) to install, using Homebrew as your package manager.

It should work perfectly, but is also untested.

# Usage
  1. Copy and paste the `template` folder somewhere
  2. Rename it to the name of the playlist or channel you're downloading, or just call it videos or something.
  3. Open a terminal/command prompt in the folder
  4. Run `youtube-dl.exe --config-location archive.conf [Your video/playlist/channel URL]`
  5. Wait for the videos to download. (You can start/stop this any time by using `Ctrl-C`, progress will be saved.)
  6. Run `youtube-dl --download-archive srv3.tracker --skip-download --sub-format srv3 --all-subs --write-sub [Your video/playlist/channel URL]` to back up YouTube-native subtitles that preserve formatting, such as seen [here (on desktop browsers)](https://www.youtube.com/watch?v=QvO8kcWFFT0). Sadly no way to play these back yet, but it shouldn't be too complicated to put one together, so these are certainly worth saving.

If something isn't working, please open an [issue](https://github.com/oofdere/easy-yt-archival/issues/new).

# Updating
To update youtube-dl, just use the following command
```sh
youtube-dl -U
```
All the other dependencies should be handled by your package manager.

Hopefully none of the files in this repo will need an update.