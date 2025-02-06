# Search & Replace - MusicBee Basic

Regular expressions used in musicbee default search and replace tool.

## Change "A - B" to "B - A"

Search：
>(.+?)\s-\s(.+)

Replace：
>$2 - $1

Example："Cantiga – 384" → "384 - Cantiga"

## Change "A - B C" to "B - A C"

Search：
>(.+?)\s-\s(.+?)\s(.+)

Replace：
>$2 - $1 $3

Example："Cantiga - 384 A que por muy" → "384 - Cantiga A que por muy"

## Add annotation text with the parenthesis to the end

Search:  
>(.+)  

Replace:  
>$1 (Live)

Example: "Cantiga" → "Cantiga (Live)"

## Remove quotation marks

Search:  
>'(.+)'

or  
>"(.+)"

If its content should be kept:  
Replace:
>$1

If its content should be remove:  
Replace:
>empty

Example: "Cantiga '384'" → "Cantiga 384"

Note: For moving the content inside to another tag in musicbee, check advanced page.  

## Remove parenthesis

Search:  
>(\\(.+\\))

If its content should be kept:  
Replace:
>$1

If its content should be remove:  
Replace:
>empty

Example: "Cantiga 384 (Alfonso)" → "Cantiga 384"

## Trim the space at either the beginning or the end

Search:  
>^\s+|\s+$

Replace:  
>empty

Example: " Cantiga 384 " → "Cantiga 384"

## Only keep the content before first dot

Search:  
>(.+?)\\.(.*)

Replace:  
>$1

Example: "Cantiga 384. A que por muy" → "Cantiga 384"

## Classical Music Title Format one - Waltz

Search: Waltz\s(.+)\s(in\s[A-Z]\s(Flat|Sharp)\s(Major|Minor))(.*)

Replace: Waltz $2, $1$5

Exmple: Waltz Op. 64: No.1 in A Minor - Dance -> Waltz in A Minor, Op. 64: No.1 - Dance
