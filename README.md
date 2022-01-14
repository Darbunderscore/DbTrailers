# DbTrailers

This project is a fork of [TheaterTrailers](https://github.com/Electronickss/TheaterTrailers) by [Electronickss](https://github.com/Electronickss) and 99% of the code is still his. Other contributors are: [TristBella](https://github.com/TristBella).

This is a Python script that automates the downloading of movie trailers from YouTube using youtube-dl. Moive trailers are downloaded if their release date hasn't been reached. The videos will auto-delete when the movie is released. Files and folders are named with the standard naming convetions of  Plex and The Movie DB. A "Coming Soon" image is copied in as `poster.jpg` and two versions of the trailer are stored. One is stored with `-trailer` in the name so Plex recognizes it as the trailer and the other is recognized as the movie.
## Fixes/Changes
1. checkcashe function: Made it compatible with python3.
2. videodownloader function: Delete the youtube_dl cache before each download to cut down on 403: forbidden errors
3. videodownloader function: Added a 3 second pause after download to account for post-processing and eliminate file copy errors
4. videodownloader function: Performing a chmod on the downloaded file to 755 to resolve access issues if your using a different user for the cron job
5. videodownloader function: Fixed some glitches with file copies when you're using a custom library location in the .config
6. Misc. fixes by TristBella via [theatertrailers.txt](https://github.com/Electronickss/TheaterTrailers/files/6013437/theaterTrailers.txt) 
---
# Why?

This application adds to the cinematic feel of your Plex setup by adding trailers of unreleased movies to your library.

---

# Screenshot

![Plex Web View](http://i.imgur.com/uEwB02G.png)

---

# Installation


### From withing your OS

1. Install Python. This module supports 2.7.x. 3.x support can be spotty. Raise a github issue if you spot a compatibility error
   * Python for Windows can be found [here](https://www.python.org/downloads/windows/)
2. Install PIP if it isn't already present
   * Check [this out](https://pip.pypa.io/en/stable/installing/) for help
3. Install [youtube_dl](https://rg3.github.io/youtube-dl/index.html)
   * `pip install --upgrade youtube_dl`
4. Install [tmdbsimple](https://pypi.python.org/pypi/tmdbsimple)
   * `pip install tmdbsimple`
5. Sign up at The Movie DB for an account and [get a personal api key](https://www.themoviedb.org/documentation/api)
   * A walk-through can be found [here](https://github.com/Electronickss/TheaterTrailers/wiki/Signing-up-for-a-TMDB-API-Key)
6. *(Optional)* Get your Plex token off of Plex Web
7. Clone this repository or download it where you want it
   * git clone suggested
8. Edit the config file to include your API keys. Remove `example` from the `trailers.conf` file title. Adjust other settings as necessary
9. This script can be run manually like any other script or configured with Cron/Windows Task Scheduler.
   * Cron examples can be found [here](https://github.com/Electronickss/TheaterTrailers/wiki/Cron-Examples)

### From within Plex
   
10. Add a folder inside of the Movie library that you want trailers, to `/directoryTo/TheaterTrailers/Trailers/` or `C:\directoryTo\TheaterTrailers\Trailers`
    * *Note that trailers in different libraries are not shared*

11. Enable trailers on your server
    * Check the option in `Settings > Server > Extras >  Include Cinema Trailers from movies in my library`

12. Enable trailers on your client
    * Plex Web: Set the number of trailers in  `Settings > Web > Player > Cinema Trailers to Play Before Movies`

13. TheaterTrailers copies over a "Coming Soon" poster so that users know it's a trailer. For that to be set to default, local media assets needs to be set as priority within your agents. Go to `Settings > Server > Agents` then adjust within each agent

---

# Credit

Thank you to the [youtube-dl](https://github.com/rg3/youtube-dl) team and to [Electronickss](https://github.com/Electronickss)!

This product uses the TMDb API but is not endorsed or certified by TMDb

---
