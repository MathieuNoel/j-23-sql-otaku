Écrire une requête pour récupérer les données... Pas toutes, hein, limitez à une quinzaine de lignes

SELECT * FROM viewing LIMIT 15;

Écrire une requête pour sélectionner toutes les données, rangées dans un ordre aléatoire

SELECT * FROM viewing 
ORDER BY random();

Écrire une requete pour récupérer 15 lignes de manière aléatoire

SELECT * FROM viewing 
ORDER BY random() 
LIMIT 15 ;


la moyenne d'age des viewers, classée par pays.

SELECT round(avg(viewer_age_group)) AS theAverageAgeOfViewers,viewer_country FROM viewing GROUP BY viewer_country ;

le nombre d'épisodes regardés, classé par tranche d'âge, et rangé par tranche d'age décroissant.

SELECT viewer_age_group,count(episode) as numberOfEpisode FROM viewing GROUP BY viewer_age_group ORDER BY viewer_age_group DESC;

BONUS CACTUS (attention, ça parait simple mais ça pique !) : le nombre de visionnage par an.

SELECT count(episode),extract('year' FROM viewing_date) as year FROM viewing GROUP BY year ORDER BY year;