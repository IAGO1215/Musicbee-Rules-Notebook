## Put <Composer> into <Artist (Display)> without year of birth and death
  
```
  Search: (.+)\s\( //in <Composer>
  Replace: $1 //in <Artist (Display)>
```

  
  ## Put <Composer> into <Artists: Artist> without year of birth and death, and put <Original Artist> into <Artists: Performer>
  
  ```
  1-
  Search: (.+)\s\( //in <Composer>
  Replace: $1 //in <Artist>
  2-
  Serach: (.+) //in <Original Artist>
  Replace: 
  ```
