# 🎬 movie_watcher

This is a bash script which plays episodes and seasons in order via mpv, automates delete, and saves playback position when quiting early.

# 🧐 why?

Honestly, I'm a huge fan of seeing movies and series. But I always find myself with tons of movies and series accumulating my laptop. Then I have to delete all of them which is obviously repetitive and tedious. But once a wise penguin said to me:
```bash
                         ______________________________________________
                        < Give your repetitive and tedious tasks to me >
                        ----------------------------------------------
                                              \
                                               \
                                                  .--.
                                                 |o_o |
                                                 |:_/ |
                                                //   \ \
                                               (|     | )
                                              /'\_   _/`\
                                              \___)=(___/


```
And that was the time I got started.  

# 🔐 design choices

## ⚫ Why auto_delete without prompt:
This may seems a bit weird. But the whole purpose of this project is to make repetitive and tedious tasks automatically done (which that wise penguin mentioned). Well a nice and clean prompt "Do you want to delete this episode?" simply defeat that purpose.
## ⚫ Why detecting "finished normally" with mpv's output rather than exit code:
This is interesting. In my first design, I stored exit code of mpv in a variable to differ between early quit and finishing normally. But I noticed that the exit code in both situation are the same, so it's not useful for this purpose. The output of mpv (the last line to be more precise) is the main clue.
## ⚫ How resume works:
Well, this is the section that linux made my job very simple. Mpv has a really useful switch to save playback position when quitting early which is "--save-position-on-quit". In this case, I didn't need to touch file to save playback position. Well, thank you linux for all your great commands.
## ⚫ limitations:
1- abrupt kill (like closing the terminal) won't save the position. So be careful about how you exit.

2- remember your files must be zero-padded (E01, E02, ...) otherwise it won't sort correctly. By default, linux sorts files and directories alphabetically.

# 🚀 Getting started:
This is the easy part. The only tools that you need are:

🔹bash

🔹installed mpv command

1- if you don't have mpv command installed, try this:
```bash
sudo apt update
sudo apt install mpv
```
2- make sure your movies are in ~/Videos.

3- now simply clone this into your terminal:

```bash
git clone https://github.com/AliSabetDeveloper/movie_watcher.git
```
4- go to movie_watcher directory and run the script:
```bash
cd movie_watcher
bash movie_watcher
```
5- enjoy your shows - and let the script handle the cleanup.

                                                made with ❤️ and linux
