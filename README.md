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

).



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



Video Walkthrough: YouTube Demo

Let me know if you’d like to add specific DAX formulas or dataset samples!

New chat





