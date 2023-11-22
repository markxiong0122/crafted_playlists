# TuneCraft: Spotify Playlist Generator

[![GitHub license](https://img.shields.io/badge/license-Apache-blue.svg)](
https://github.com/yourusername/TuneCraft/blob/master/LICENSE)

## Table of Contents

+ [About](#about)
+ [Getting Started](#getting_started)
  + [Prerequisites](#prerequisites)
+ [Installing the requirements](#installing)
  + [Using the Makefile](#installing_makefile)
+ [Running the code](#run_locally)
  + [Execution Options](#execution_options)
    + [main.py](#src_main)
    + [Usage Examples](#usage_examples)
+ [Todo](#todo)
+ [License](#license)

## About <a name = "about"></a>

TuneCraft is a unique Spotify playlist generator that creates new playlists based on your existing playlists, musical taste, and specified criteria. Designed to help you explore new music while maintaining a familiar sound, TuneCraft ensures that it recommends new songs by checking all your liked songs and songs that exist in your playlists.

The main code is located in the main.py file. Functions for interacting with the Spotify API and generating playlists can be found in the same file.

## Getting Started <a name = "getting_started"></a>

These instructions will get you a copy of the project up and running on your local machine.

### Prerequisites <a name = "prerequisites"></a>

You need to have a machine with Python >= 3.6 and any Bash-based shell (e.g. zsh) installed.

```ShellSession
$ python3.10 -V
Python 3.10

$ echo $SHELL
/usr/bin/zsh
```

## Installing the requirements <a name = "installing"></a>

### Using the Makefile <a name = "installing_makefile"></a>
All the installation steps are being handled by the [Makefile](Makefile).

Then, to create a conda environment, install the requirements, setup the library and run the tests
execute the following commands:

```ShellSession
$ make create_env
$ conda activate tunecraft
$ make requirements
```

## Running the code <a name = "run_locally"></a>

### Execution Options <a name = "execution_options"></a>

First, make sure you are in the correct virtual environment:

```ShellSession
$ conda activate tune_craft

$ which python
/home/<user>/anaconda3/envs/src/bin/python
```

#### main.py <a name = "src_main"></a>

Now, in order to run the code you can call the [main.py](main.py)
directly.

```ShellSession
$ python main.py -h
usage: main.py -u USER_ID [-s SEED_PLAYLIST] [-nt NUMBER_TRACKS] [--new-artists] [--refresh] [-pl -LIST_PLAYLISTS] [-gl LIST-GENRES] [-h HELP] [-g GENRE] [-bpm BPM]

TuneCraft - Spotify Playlist Generator


Optional Arguments:
  -s SEED_PLAYLIST, --seed-playlist SEED_PLAYLIST
                        The seed playlist ID to generate a new playlist from
  -nt NUMBER_TRACKS, --number-tracks NUMBER_TRACKS
                        Number of tracks in the generated playlist
  --new-artists         Include only new artists
  --refresh             Refresh the local database from Spotify
  -pl --list-playlists  List all your playlists
  -gl --list-genres     List all genres
  -g --genre            Include only the input genre
  -bpm --bpm            Include only tracks with the specified tempo
  -h, --help            Show this help message and exit


```

#### Usage Examples <a name="usage_examples"></a>

Get all playlists under the user's account and corresponding IDs:

  ```ShellSession
  $ python main.py -pl
  ```
  - You should expect something like:
    ```ShellSession
    $ Welcome to Spotify Playlist Generator!
      Your playlists:
      5cvqOBnWyutLDR9gn2qGCP: #RECENT
      4kihcTS1QYwAtKjkAtabkP: House
      6gkpeoYoAEKjFgnAvLAaLK: 蹦
      5M9qy5FiKU0wSPZOWglrMO: jazz hiphop
    ```

Generate a new playlist based on a seed playlist ID with 20 tracks:

```ShellSession
$ python main.py -u your_user_id -s your_seed_playlist_id -nt 20
```

Generate a new playlist with only new artists:

```ShellSession
$ python main.py -u your_user_id -s your_seed_playlist_id --new-artists
```

List all your playlists:

```ShellSession
$ python main.py -u your_user_id --list-playlists
```

Refresh the local database and list all your playlists:

```ShellSession
$ python main.py -u your_user_id --refresh --list-playlists
```


Todo <a name = "todo"></a>

Add support for generating playlists based on moods and genres.
Implement a web interface for easier user interaction.
Improve the playlist generation algorithm for better recommendations.

Available Genre: 
Available Genre: {'genres': ['acoustic', 'afrobeat', 'alt-rock', 'alternative', 'ambient', 'anime', 'black-metal', 'bluegrass', 'blues', 'bossanova', 'brazil', 'breakbeat', 'british', 'cantopop', 'chicago-house', 'children', 'chill', 'classical', 'club', 'comedy', 'country', 'dance', 'dancehall', 'death-metal', 'deep-house', 'detroit-techno', 'disco', 'disney', 'drum-and-bass', 'dub', 'dubstep', 'edm', 'electro', 'electronic', 'emo', 'folk', 'forro', 'french', 'funk', 'garage', 'german', 'gospel', 'goth', 'grindcore', 'groove', 'grunge', 'guitar', 'happy', 'hard-rock', 'hardcore', 'hardstyle', 'heavy-metal', 'hip-hop', 'holidays', 'honky-tonk', 'house', 'idm', 'indian', 'indie', 'indie-pop', 'industrial', 'iranian', 'j-dance', 'j-idol', 'j-pop', 'j-rock', 'jazz', 'k-pop', 'kids', 'latin', 'latino', 'malay', 'mandopop', 'metal', 'metal-misc', 'metalcore', 'minimal-techno', 'movies', 'mpb', 'new-age', 'new-release', 'opera', 'pagode', 'party', 'philippines-opm', 'piano', 'pop', 'pop-film', 'post-dubstep', 'power-pop', 'progressive-house', 'psych-rock', 'punk', 'punk-rock', 'r-n-b', 'rainy-day', 'reggae', 'reggaeton', 'road-trip', 'rock', 'rock-n-roll', 'rockabilly', 'romance', 'sad', 'salsa', 'samba', 'sertanejo', 'show-tunes', 'singer-songwriter', 'ska', 'sleep', 'songwriter', 'soul', 'soundtracks', 'spanish', 'study', 'summer', 'swedish', 'synth-pop', 'tango', 'techno', 'trance', 'trip-hop', 'turkish', 'work-out', 'world-music']}

License <a name = "license"></a>

This project is licensed under the Apache License - see the LICENSE file for details.
