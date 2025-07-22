Spotify Listening History Analysis - Power BI Dashboard
Project Overview
This Power BI dashboard analyzes personal Spotify streaming data to uncover listening trends, top artists/albums/tracks, and hourly/daily playback patterns. The interactive report helps visualize music consumption habits over time.
Key Features
✔ Top Stats: Most-played artists, albums, and tracks.
✔ Time Analysis: Listening trends by hour, day, and year.
✔ Interactive Filters: Filter by platform (mobile/desktop), shuffle mode, and skipped tracks.
✔ Metrics: Average listening duration, repeat plays, and skip rates.
Tools Used
Power BI (Data modeling, visualization)

Power Query (Data cleaning)

How to Use
Download your Spotify data (JSON format).

Import into Power BI using the provided transformations.

Explore trends with the interactive dashboard.
Key Questions Explored
Listening Habits:

When do I listen to music most (hourly/daily trends)?

How has my music consumption changed year-over-year?

Content Preferences:

Who are my top 10 most-played artists?

Which albums and tracks do I replay most often?

Playback Behavior:

How often do I skip tracks or use shuffle mode?

What’s my average listening duration per session?

Problems & Challenges
Data Quality: Raw JSON data required cleaning (e.g., handling null values, standardizing timestamps).

Time-Zone Adjustment: UTC timestamps were converted to local time for accurate hourly trends.

Duplicate Entries: Identified and merged duplicate tracks/artists (e.g., "feat." vs. "ft.").

Performance: Optimized Power Query transformations to reduce dashboard load time.

Dataset Details
Source
Requested from Spotify via Privacy Settings (takes ~30 days to receive).

Files Used:

StreamingHistory_X.json (Listening history: timestamps, track/artist names, play duration).

endsong_X.json (Optional: Additional metadata like platform, shuffle mode).

Key Fields
Column	Description
ts	Timestamp (UTC) of playback
ms_played	Duration played (milliseconds)
track_name	Name of the track
artist_name	Name of the artist
platform	Device used (mobile/desktop)
shuffle	Whether shuffle mode was enabled
Dashboard Features
✔ Interactive Filters: Drill down by date range, platform, or shuffle mode.
✔ Visualizations:

Hourly heatmap of listening frequency.

Top artists/albums with play counts.

YoY trend comparison.
✔ Metrics: Skip rate, average play duration, repeat tracks.

Tools & Techniques
Power BI: DAX measures, custom visuals (e.g., heatmaps).

Power Query: Merged JSON files, cleaned data, added calculated columns (e.g., local time).

How to Replicate
Request your data from Spotify.

Load JSON files into Power BI and apply transformations (see video tutorial).

Clone this repo or adapt the DAX/model for your dataset.

Screenshot:
https://i.imgur.com/example.png

Video Walkthrough: YouTube Demo

Let me know if you’d like to add specific DAX formulas or dataset samples!

New chat



Spotify Analysis

SPOTIFY ANALYSIS
Domain Document
 spotify_track_uri
Description: A unique identifier assigned to each track in Spotify’s database.
Format: "spotify:track:<base-62 string>" (e.g., spotify:track:3n3Ppam7vgaVa1iaRUc9Lp).
Purpose: Helps link tracks to their metadata and allows for cross-referencing with Spotify’s catalog.
 ts (Timestamp)
Description: The exact time (in UTC) when the track stopped playing.
Format: ISO 8601 format (e.g., 2024-02-07T14:30:45Z).
Purpose: Used for analyzing listening patterns, session durations, and track end times.
 platform
Description: The device or platform used to stream the track.
Possible Values:
"desktop" (Windows/Mac app)
"mobile" (iOS/Android app)
"web" (Spotify Web Player)
"smart_speaker" (Amazon Echo, Google Home, etc.)
Purpose: Helps understand where users are consuming music.
 ms_played
Description: The total number of milliseconds the track was played before stopping or skipping.
Format: Integer value (e.g., 215000 for 3 minutes 35 seconds).
Purpose: Useful for engagement analysis, identifying completed plays, and calculating revenue (as Spotify pays artists based on streaming duration).
 track_name
Description: The title of the song being played.
Example: "Shape of You"
Purpose: Helps in analyzing the most played tracks.
 artist_name
Description: The name of the artist performing the song.
Example: "Ed Sheeran"
Purpose: Useful for ranking popular artists and identifying user preferences.
 album_name
Description: The name of the album the track belongs to.
Example: "÷ (Divide)"
Purpose: Helps analyze album popularity and user listening trends.
 reason_start
Description: The reason why the track started playing.
Possible Values:
"trackdone" (Previous track ended)
"clickrow" (User manually selected the song)
"backbtn" (User pressed back)
"fwdbtn" (User pressed next)
"playbtn" (User pressed play)
"autoplay" (Spotify automatically selected the next track)
Purpose: Helps understand user behavior and track engagement patterns.
 reason_end
Description: The reason why the track stopped playing.
Possible Values:
"trackdone" (Track finished playing)
"endplay" (User paused or stopped playback)
"fwdbtn" (User skipped to the next track)
"backbtn" (User went back to the previous track)
"logout" (User logged out or session ended)
Purpose: Helps identify why users stop listening to tracks, which is crucial for retention analysis.
 shuffle
Description: Indicates whether shuffle mode was enabled during playback.
Possible Values:
TRUE (Shuffle mode was ON)
FALSE (Shuffle mode was OFF)
Purpose: Helps analyze how often users use shuffle mode in their listening sessions.
 skipped
Description: Indicates whether the user skipped the song before it finished.
Possible Values:
TRUE (User skipped to the next track)
FALSE (User did not skip)
Purpose: Important for understanding user engagement, drop-off rates, and song popularity.


