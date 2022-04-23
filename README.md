# Historical Movie Timeline

## Overview
Since the early 20th Century, cinema has been one of the most fundamental ways that we share stories with each other. From raunchy comedies and super-heroic epics to historical fiction, there is a story in film for just about anyone. For me, historical dramas have always been of interest. Watching a movie about a long-gone event can feel like a glimpse into the past. However, these films are often highly dramatized, exaggerated, or inaccurate in the way the stories are told. Sometimes watching a movie about a particular event can feel like reading the 14th chapter of a book. It was for this reason that I decided to create a timeline of historical movies. 

The current version has over 624 movies spanning from the prehistoric to the classical era. Movies from around the globe are included, as well as remakes and alternative versions. Users can see the geographical location of each movie and data such as the credits can be found by hovering over the object in the timeline.

### Tools
- Jupyter Notebook
- TMDB API
- GeoPy library
- Tableau

<<<<<<< HEAD
## Creating the Timeline

Several techniques were employed to create the timeline, but most of the information came from a community built movie and TV database called [TMDB](https://www.themoviedb.org/?language=en-US). 

### First Attempt
The original goal was to capture all available movies with information available and putting them on the timeline. The TMDB API tool was used to collect all movies available from 1945 to 2022 that had a vote count greater than 0, rating over 3.9. The movies were filtered by searching the description for certain keywords, then further filtered by a list of anti-keywords. Due to the number of topics and potenital keywords, it was decided that the timeline would be done in segments, starting with all events occuring before 1 AD. Despite the keyword and antikeyword lists, there were still hundreds of movies that needed to be manually removed due to a limited description. In some cases, a desired movie would be removed becuase of a broad antikeyword. 

Using this method, over 120,000 movies were obtained, they were automatically filtered down to 443 movies, and then manually refined to 85 movies. Despite having such a massive pool, it was later discovered that some desired movies in the database were not captured, likely becuase of the keyword and antikeyword lists. 

Clearly this was a lengthy process, taking over 1 hour to run with additional time needed to manually refine the timeline. The potential for missing keywords and the limited timeline segments was also concerning. For these reasons, it was determined that there was likely a better way to accomplish the original goal.

### Second Attempt

After some searching, it was found that there were existing hitorical lists of movies that others had created through Wikipedia. Although several of the movies found in the original attempt were missing, it was decided that the Wikipedia lists could be used as foundation to build as opposed to scraping a hundred thousands movies and trying to filter the relevant ones, especially considering how much additional processing would go into verifying only the right movies were captured. 

The lists from wikipedia were loaded into a csv file for easy processing. The Wiki_Movie_Starter notbook was used to find the TMDB movie id so that additional information could be found from the database. The TMDB_Movie_Transform notebook was used to get the cast, director, studio, and other information using the TMDB movie ID through their API. Additional tables and calculations were created to be used as filters on the timeline.

Finally, the Add_Movies notebook was created to append the resulting files when additional movies are found. Several of the movies captured from the first attempt were added to the movie_list file to test it.

# Results

There are currently 624 movies on the list, many from studios outside of the US. Movies released as early as 1911 are included. The timeline spands from 80,000 BC to 1,900 AD. 

The timeline was created with Tableau and can be adjusted by the user in several ways. The size of the marker is determined by movie popularity on TMDB, while the color is determined by the longtitude of the represented location. 

The timeline can be filtered by directors and actors. Recurrance was a main theme for the timeline, this was done to augment the storytelling. In this way you can see some of the same faces through time as different characters. The Actor Recurrance Score (ACR) allows users to see which movies have a high number of reccuring actors. This was calculated by summing the credits for every actor/actress with more than 1 appearance, then adding all of the reccuring actor/actress appearances to each movie where they are featured.

At the moment, the timeline does include movies with mythological settings. This was allowed as a means to show some of the themes of the time. Not all, and in fact many, of the movies are historically inaccurate. Although this timeline will hopefully provide the viewer with some historical context, it alone is not meant to serve as a course in world history.

# Conclusions

Aside from creating a movie list for entertainment, I hope that this project can also be useful to educators. Although many of the movies on the timeline take liberties, they serve as an example of how stories and history can be skewed by the people revealing it. In this way, several topics related to history and cinema such as white-washing and oversexualization can be analyzed. By looking at movies from different countries and release years, we can see the ways in which stories and history can be told from different perspectives, as well as the values of the time. 

# Next Steps

So far, this has been a one man project. The intention of the author was to learn a little about world history and cinema through the films on the list. That being said, there may be several mistakes that seasoned historians and cinephiles find that may have been missed. There may also be movies that this list does not capture. To make this project as effective as possible, the author will seek additional assistance on social media to idenify errors and improvements. The greatest hope is that others will be inspired by this project and want to build upon it. 

### Contact 
Email: sean.cary62@gmail.com
=======
# Testing Embedded Dashboard
 ```js

  <div class='tableauPlaceholder' id='viz1650055503144' style='position: relative'><noscript><a href='#'><img alt='Historical Movie Timeline ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;4S&#47;4SWJ889KQ&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='path' value='shared&#47;4SWJ889KQ' /> <param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;4S&#47;4SWJ889KQ&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /><param name='filter' value='publish=yes' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1650055503144');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1200px';vizElement.style.height='1152px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1200px';vizElement.style.height='1152px';} else { vizElement.style.width='100%';vizElement.style.height='1927px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>
  ```

#Testing Commits
>>>>>>> b28f6696a07fbd586fedd989865740260b7bcb26
