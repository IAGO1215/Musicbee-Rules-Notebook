Regular expressions used in musicbee basic search and replace tool.

## 1-Change the word order of the title

Search：\s-\s(.+?)\s

Replace：$1 - 

Example：Cantiga – 384 Flor des Flores → Cantiga 384 – Flor des Flores

## 2-Add annotation text inside the parenthesis at the end of the title

Search: (.+)

Replace: $1 (Live)

Example: Cantiga → Cantiga (Live)

## 3-Remove unnecessary quotation marks

Search: '(.+)' or "(.+)"

Replace: $1

Example: Cantiga '384' → Cantiga 384

## 4-
