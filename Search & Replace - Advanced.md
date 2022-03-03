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
## Put number serials into track titles
  ```
  1-
  Warning: Renumber track without "Padding" and "Disc Reset"
  Search: (.+) //in <#Track>
  Replace:  $1 //Append in <Title>
  2-
  Search: Mazurka\sNo\.\s(.+)\s(.?\d)$ //in <Title>
  Replace: Mazurka No. $2 $1
  ```
  
  Example: 1-8 Mazurka in A-Flat Major, Op. 7: No. 4 → 1-08 Mazurka No. 8 in A-Flat Major, Op. 7: No. 4
 
##  
  
  
