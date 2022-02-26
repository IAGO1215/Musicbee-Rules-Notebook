## Lowercase the letter before ' and keep the letter after ' uppercase
```
Field: TITLE
Rex: (.?)'(.?)
Replace: $lowercase($1)'$uppercase($2)
```
Example: l'amour -> l'Amour
