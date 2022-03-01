Regular expressions used in musicbee basic search and replace tool.

## 1-Change the word order of the title

Search：\s-\s(.+?)\s

Replace：$1 - 

Example：Cantiga – 384 Flor des Flores → Cantiga 384 – Flor des Flores

## 2-Add annotation text with the parenthesis at the end of the title

Search: (.+)

Replace: $1 (Live)

Example: Cantiga → Cantiga (Live)

## 3-Remove unnecessary quotation marks but keep the content inside

Search: '(.+)' or "(.+)"

Replace: $1

Example: Cantiga '384' → Cantiga 384

Note: For moving the content inside to another tag in musicbee, check advanced page. 

## 4-Remove parenthesis and its content

Search: (\\(.+\\))

Replace: 

Example: Cantiga 384 (Alfonso) → Cantiga 384

## 5-Trim the space at the end of the title

Search: (.+)\s

Replace: $1

Example: Cantiga 384  → Cantiga 384

## 6-Seperate two words with space on each side of symbol /

Search: (.+?)/(.+?)

Replace: $1 / $2

Example: Cantiga/384 → Cantiga / 384

## 7-Only keep the content before first dot .

Search: (.+?)\\.(.*)

Replace: $1

Example: Cantiga 384. A que por muy. Flor → Cantiga 384

Note: .+? is lazy ; .+ is greedy

## 8-Classical Music Title Format one - Waltz

Search: Waltz\s(.+)\s(in\s[A-Z]\s(Flat|Sharp)\s(Major|Minor))(.*)

Replace: Waltz $2, $1$5

Exmple: Waltz Op. 64: No.1 in A Minor - Dance -> Waltz in A Minor, Op. 64: No.1 - Dance
