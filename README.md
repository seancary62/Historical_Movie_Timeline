# Historical Movie Timeline

## Overview
Since the early 20th century, cinema has been one of the most fundamental ways that we share stories with each other. From raunchy comedies and super-heroic epics to historical fiction, there is a story in film for just about anyone. For me, historical dramas have always been of interest. Watching a movie about a long-gone event can feel like a glimpse into the past. However, these films are often highly dramatized, exaggerated, or inaccurate in the way they tell the story. Sometimes watching a movie about a particular event can feel like jumping to the 14th chapter of a book. It was for this reason that I decided to create a timeline of historical movies. 

The current version has over 624 movies spanning from the prehistoric to the classical era. Movies from around the globe are included, as well as remakes and alternative versions. Users can see the geographical location of each movie and data such as the credits can be found by hovering over the object in the timeline.

### Tools
- Jupyter Notebook
- TMDB API
- GeoPy library
- Tableau

## Creating the Timeline

Several techniques were employed to create the timeline, but most of the information came from a community built movie and TV database called [TMDB](https://www.themoviedb.org/?language=en-US). 

### First Attempt
The first attempt was to capture all historical dramas on TMDB and add them to the timeline. The TMDB API was used to collect all movies available from 1945 to 2022 that had a vote count greater than 0 and rating over 3.9. The movies were filtered by searching the description for certain keywords and then filtered further by a list of anti-keywords. Due to the number of topics and potenital keywords, it was decided that the timeline would be done in segments, starting with all events occuring before 1 AD. Despite the keyword and antikeyword lists, there were still hundreds of movies that needed to be manually removed due to a limited description. In some cases, a desired movie would be removed becuase of a broad antikeyword. 

Using this method, over 120,000 movies were obtained,  filtered by code down to 443 movies, and then manually refined to 85 movies. This was clearly a long process, taking over 1 hour to run with additional time needed to manually refine the timeline. The potential for missing keywords and the limited timeline segments was also concerning. For these reasons, it was determined that there was likely a better way to accomplish the original goal.

### Second Attempt

Several existing historical movie lists were found on Wikipedia. Although many of the movies found in the original attempt were missing, it was decided that the new lists could be used as foundation to build on as opposed to gathering thousands of movies and trying to filter the relevant ones.

The lists from Wikipedia were loaded into a csv file for easy processing. The Wiki_Movie_Starter notbook was used to find the TMDB movie id so that additional information could be found from the database. The TMDB_Movie_Transform notebook was used to get the cast, director, studio, and other information using the TMDB movie ID through their API. Additional tables and calculations were created to be used as filters on the timeline.

Finally, the Add_Movies notebook was created to append the cleaned files when additional movies are found. Several of the movies captured from the first attempt were added to the movie_list_clean file.

## Results

<div class='tableauPlaceholder' id='viz1650727903504' style='position: relative'><noscript><a href='#'><img alt='Historical Movie Timeline ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Hi&#47;HistoricalMovieTimelineComplete&#47;HistoricalMovieTimeline&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='HistoricalMovieTimelineComplete&#47;HistoricalMovieTimeline' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Hi&#47;HistoricalMovieTimelineComplete&#47;HistoricalMovieTimeline&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /><param name='filter' value='publish=yes' /></object></div>     

#### Live Timeline:

[Historical-Movie-Timeline](https://public.tableau.com/app/profile/sean.cary/viz/HistoricalMovieTimelineComplete/HistoricalMovieTimeline?publish=yes)


There are currently 624 movies on the list, many from studios outside of the US. Movies released as early as 1911 are included and the timeline spands from 80,000 BC to 1,900 AD. 

The timeline was created with Tableau and can be adjusted by the user in several ways. The size of the marker is determined by movie popularity on TMDB, while the color is determined by the longtitude of the represented location. 

Recurrance was a main theme for the timeline, this was done to augment the storytelling. In this way you can see some of the same faces through time as different characters. The Actor Recurrance Score (ACR) allows users to see which movies have a high number of reccuring actors. This was calculated by summing the credits for every actor/actress with more than 1 appearance, then adding all of the reccuring actor/actress appearances to each movie where they are featured.

At the moment, the timeline does include movies with mythological and religious settings. This was allowed as a means to show some of the themes of the time. 

## Conclusions

Although the movie list was built mostly for entertainment, I hope that this project can also be useful to educators. Although the movies on the timeline take liberties, they serve as an example of how stories and history can be skewed by the ones telling it. In this way, several topics related to history and cinema such as white-washing and oversexualization can be analyzed. By looking at movies from different countries and release years, we can see the ways in which stories can be told from different perspectives, as well as the values of the ones telling it.

## Next Steps

So far, this has been a one man project. My intention was to learn a little about world history and cinema through the films on the list. That being said, there may be several mistakes that seasoned history buffs and cinephiles might find. There are also lots of movies that are missing. The new objective is to capture as many movies from as many perspectives as possible.

To make this a reality, I'll be looking for contributors online to help build the list, add context to the films, and hopefully create linkable discussions about what the movies get right or wrong. 

If interested, please reach out to the contact below!

### Contact 
Email: sean.cary62@gmail.com

### Resources
- [TMDB](https://www.themoviedb.org/?language=en-US)
- [List of historical films set in Near Eastern and Western civilization
](https://en.wikipedia.org/wiki/List_of_historical_films_set_in_Near_Eastern_and_Western_civilization)
- [List of historical films set in Asia
](https://en.wikipedia.org/wiki/List_of_historical_films_set_in_Asia)