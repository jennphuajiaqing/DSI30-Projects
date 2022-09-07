<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Capstone Project: Board Games Recommender System

### Author: Phua Jia Qing
---

### Overview:

- Backgorund & Problem Statement
- Cleaning & EDA
- Data Dictionary
- Collaborative Filtering
- Matrix Factorization
- Conclusion & Future Works

---

### Data

Link: ([*source*](https://www.kaggle.com/datasets/jvanelteren/boardgamegeek-reviews?datasetId=211744&sortBy=voteCount&select=games_detailed_info.csv)). 

---

## Background & Outside Research

#### **History of Board Games**
In 3000BC, one of the earliest physical board games, Senet, is first played across Ancient Egypt. The game, which was only seen in the courts of royalty and the upper classes, is the first example of a physical object created for the purposes of a game. Although Senet’s rules are not entirely known, it is featured in ancient hieroglyphs, where it is described as ‘the game of passing’.

In 1900, in Arden, Delaware (US), artist and anti-monopoly protestor Elizabeth Magie creates the first version of her game The Landlord's Game. The game was originally designed as a protest against unfair taxation and monopoly laws in the US, and was later copied and sold to the Parker Brothers Co in the 1930s as the game Monopoly. In 2015 Hasbro (who now own the rights) announced over 1 billion games of Monopoly had been sold worldwide, making it the most popular board game ever created.

In 1995, the first copy of popular German game Settlers of Catan is produced. The hugely popular game is famous as the first Eurogame to ‘break America’, leading to the growing popularity of European-style tabletop games in the US.

Currently in 2020s, there is a worldwide emergence of hybrid games combining multiple genres.

One can understand more from ([*source*](https://boardgamegeek.com/blogpost/67680/timeline-board-game-history)).

## Problem Statement

Currently most of the methods that people use to seek board game recommendations are video reviews and forum discussion. These are not personalized. The same 'mainstream' games will always be suggested by these platforms.

Hence, as part of a data science team partnered with BoardGameGeek, we want to build a good board game recommender which addresses the following:



1.   Attend to every user's personal needs
2.   Attract new users to BGG community

--------

## Data Dictionary




### 'final_games'




| **Feature**           | **Description**                                                                                                                                                                                                     |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| id                    | Board game's ID on BoardGameGeek database.                                                                                                                                                                          |
| year                  | Board game's year of release.                                                                                                                                                                                       |
| rank                  | Board game's overall ranking on the BGG website.                                                                                                                                                                    |
| average               | Board game's average rating given by the BGG community (On a scale of 1-10, 10 being the best while 1 being the worst).                                                                                             |
| bayes average         | Board game's average rating using the Bayesian method.                                                                                                                                                              |
| users rated           | Total number of votes on rating the board game by the BGG community.                                                                                                                                                |
| _age_                 | Board game's age as of 2022.                                                                                                                                                                                        |
| description           | Description of the board game.                                                                                                                                                                                      |
| minplayers            | Minimum number of players for the board game by design.                                                                                                                                                             |
| maxplayers            | Maximum number of players for the board game by design.                                                                                                                                                             |
| suggested_num_players | Best number of players for the board game as suggested by the BGG community.                                                                                                                                        |
| suggested_playerage   | Best age for players to play the board game by design.                                                                                                                                                              |
| playingtime           | How language-dependent components (aside from the rules) are for those who do not speak the game published language (On a scale of 1-5, 5 means no necessary in-game text, 1 means unplayable in another language). |
| minplaytime           | Minimum time required for a single play-through of the board game as stated by the designer.                                                                                                                        |
| maxplaytime           | Maximum time required for a single play-through of the board game as stated by the designer.                                                                                                                        |
| minage                | Minimum age for players to play the board game by design.                                                                                                                                                           |
| boardgamecategory     | Board game's associated categories (e.g. Adventure, Exploration, Fantasy, etc.).                                                                                                                                    |
| boardgamemechanic     | Board game's associated mechanics (e.g. Acting, Memory, Drafting, etc.).                                                                                                                                            |
| boardgamedesigner     | Designer(s) of the board game.                                                                                                                                                                                      |
| boardgameartist       | Artist(s) of the board game and its components.                                                                                                                                                                     |
| boardgamepublisher    | Publisher(s) of the board game.                                                                                                                                                                                     |
| strategy game rank    | Board game's under the category 'strategy' overall ranking on the BGG website.                                                                                                                                      |
| family game rank      | Board game's under the category 'family' overall ranking on the BGG website.                                                                                                                                        |
| party game rank       | Board game's under the category 'party' overall ranking on the BGG website.                                                                                                                                         |
| abstract game rank    | Board game's under the category 'abstract' overall ranking on the BGG website.                                                                                                                                      |
| thematic rank         | Board game's under the category 'thematic' overall ranking on the BGG website.                                                                                                                                      |
| war game rank         | Board game's under the category 'war' overall ranking on the BGG website.                                                                                                                                           |
| customizable rank     | Board game's under the category 'customizable' overall ranking on the BGG website.                                                                                                                                  |
| children's game rank  | Board game's under the category 'children' overall ranking on the BGG website.                                                                                                                                      |
| rpg item rank         | Board game's under the category 'rpg item' overall ranking on the BGG website.                                                                                                                                      |
| accessory rank        | Board game's under the category 'accessory' overall ranking on the BGG website.                                                                                                                                     |
| video game rank       | Board game's under the category 'video' overall ranking on the BGG website.                                                                                                                                         |
| amiga rank            | Board game's under the category 'amiga' overall ranking on the BGG website.                                                                                                                                         |
| commodore 64 rank     | Board game's under the category 'commodore 64' overall ranking on the BGG website.                                                                                                                                  |
| arcade rank           | Board game's under the category 'arcade' overall ranking on the BGG website.                                                                                                                                        |
| atari st rank         | Board game's under the category 'atari st' overall ranking on the BGG website.                                                                                                                                      |
| _name-year_           | Board game's name in English and board game's year of release. (There are games with the same name but released in different year as they are different version of the same game).                                  |


### 'reviews'



| **Feature**        | **Description**                                                                                         |
|--------------------|---------------------------------------------------------------------------------------------------------|
| user               | User's name on BoardGameGeek database.                                                                  |
| rating             | Board game's rating given by each user (On a scale of 1-10, 10 being the best while 1 being the worst). |
| comment            | User's comment on the board game on the BGG website.                                                    |
| id                 | Board game's ID on BoardGameGeek database.                                                              |
| name               | Board game's name on BoardGameGeek database.                                                            |
| n_games_user_rated | Number of board game each user rated.                                                                   |
| n_user_rated_games | Number of user rated each board game.                                                                   |


--------


## Future Works

The following are some areas that we can improve and test more for future works:



1.   We can try other evaluation metric like precision@K and recall@K.
2.   We can also try out content-based filtering and do a hybrid recommender system with both collaborative filtering and content-based filtering.
