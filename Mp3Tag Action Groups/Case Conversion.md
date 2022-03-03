## Lowercase the letter before ' and keep the letter after ' uppercase, except the initial letter of the title 
```
Field: TITLE
Rex: \s(.?)'(.?)
Replace:  $lowercase($1)'$uppercase($2)
```
Example: l'amour -> l'Amour
