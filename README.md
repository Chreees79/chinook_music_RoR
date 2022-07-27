# Réponses aux questions pour la BDD de chinook Music

![chris](./app/assets/images/music.jpg)



## a) Niveau facile

  - Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?

  ``Album.count
    => 347``

  - Qui est l'auteur de la chanson "White Room" ?

  ``Track.find_by(title: "White Room").artist
       => "Eric Clapton"```

  - Quelle chanson dure exactement 188133 milliseconds ?

  `` Track.find_by(duration: 188133).title
      => "Perfect" ```

  - Quel groupe a sorti l'album "Use Your Illusion II" ?

  ``Album.find_by(title: "Use Your Illusion II").artist
      => "Guns N Roses"```


## b) Niveau moyen

  - Combien y a t'il d'albums dont le titre contient "Great" ?

  ``Album.where("title like ?", "%great%").count
    => 13 ```

  - Supprime tous les albums dont le nom contient "music".

  ``Album.where("title like?", "%music%").destroy_all```

  - Combien y a t'il d'albums écrits par AC/DC ?

  ``Album.where("artist like ?", "AC/DC").count```

  - Combien de chanson durent exactement 158589 millisecondes ?

  ``Track.where("duration like ?", 158589).count```

## c) Niveau difficile
     Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

  - puts en console tous les titres de AC/DC.

  `` Track.where("artist like ?", "AC/DC").each do |track|
    puts track.title
    end```

  - puts en console tous les titres de l'album "Let There Be Rock".

  `` Track.where("album like ?", "Let There Be Rock").each do |track|
      puts track.title
    end``

  - Calcule le prix total de cet album ainsi que sa durée totale.

  ``Track.where("album like ?", "Let There Be Rock").sum(:price)
    Track.where("album like ?", "Let There Be Rock").sum(:duration)```

 - Calcule le coût de l'intégralité de la discographie de "Deep Purple".

  ``Track.where("artist like ?", "Deep Purple").sum(:price)```

  -Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.

  ``Track.where("artist like ?", "Eric Clapton").each do |track|
    track.update(artist: "Britney Spears")
    end```
    

MERCI DE TA VISITE !!
========================













