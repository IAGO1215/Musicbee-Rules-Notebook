# Case Conversion Rules

## Preface

The case convention of track titles is a subjective topic. 

The mostly used ones are probably the **title case** / **the sentence case** / **the proper case**. Please note that the names of these cases are unofficial and may vary depending on the source or context.

The title case refers to the style where the initial letter of each word in the track title is in upper case. For example, "**In The Middle Of The Night**" by Within Temptation is in the title case.  

The sentence case is that only the first letter is capitalized, while all other words in the track title are in lower case. For example, "**In the middle of the night**" by Within Temptation is in the sentence case.  

The proper case refers to the style where the initial letter of each word in the track title is in upper case, unless they are some "small words" like some articles, prepositions and conjunctions. For example, "**In the Middle of the Night**" by Within Temptation is in the proper case.  

Note that special nouns like persons' names, locations and other proper nouns are not affected by any case convention, hence their initial letters always in upper case or even all letters in upper case. For example, "**Jesus**", "**New York**" and "**UNESCO**" never change their cases.  

Tracks whose genre(s) belong to classical music have their own unique case convention rulesets, as the opus names and numbers are always involved.  

In my case, I prefer using the proper case, although it requires lots of extra work to implement correctly.  

The case conversion is performed exclusively in MP3Tag via a series of custom actions.  

## Articles, Prepositions and Conjunctions

Some articles, prepositions and conjunctions in each language should be always in lower case when not at the beginning of a sentence.  

The articles in all languages should be in lower case without exception.  

The choices of prepositions and conjunctions are subjective, but generally, if a word only has a few letters, it should be in lower case.  

### English
>a|an|the|of|from|with|without|or|in|at|on|over|as|for|and
### Italian
>il|la|lo|i|le|gli|di|del|della|delle|dello|da|dal|dalla|dalle|dallo|con|col|senza|o|in|nel|nella|nelle|nello|sopra|sotto|su|sul|sulla|sulle|sullo|a|al|alla|alle|allo|per|ad
### French
>le|la|les|des|du|au|à|en|de|pour|sans|avec|sur|sous|par|vers
### Spanish
>el|la|los|las|de|del|por|para|y|o|in|i|al|con|sin
### Russian
>и|или|либо|в|на|из|с|от|к|о|об|для|без|по|про|через|под|над|при|мимо|вокруг|среди|после|до|во|пока
### German (Generally should be prevented from case conversion due to initial letters of nouns in German are always in upper case)
>ein|eine|einen|einem|einer|eines|der|die|das|dem|den|des|von|vom|zu|zur|zum|ans|aufs|aus|mit|ohne|oder|in|bei|auf|über|als|für|und
### Greek
>Ο|Του|Τον|Οι|Των|Τους|Η|Της|Την|Οι|Τις|Το|Τα|Και|Ή|Αν|Σε|Από|Με|Για|Μετά|Πριν|Με|Χωρίς|Περί|Κατά|Από|Πάνω|Κάτω|Στο|Γύρω|Ανάμεσα|Εκτός|Δίπλα|Για|Ένας|Ενός|Έναν|Ενών|Έναν|Μία|Μίας|Ένα|Στα|Κι|Στο|Στον|Αν|Στη
### Latin
>ab|ad|cum|de|ex|in|inter|per|pro|sine|sub|et|aut|sed|nec|neque|si|quia|ut|dum|nam
### Danish\Norwegian\Swedish\Icelandic
>den|det|de|en|et|en|ett|a|an|i|på|af|til|med|fra|om|over|under|ved|og|eller|men|så|fordi|hvis|at|av|från|över|vid|och|att|för|í|á|frá|til|með|um|undir|yfir|við|eða|svo|því|ef|að
### Portuguese
>o|a|os|as|um|uma|uns|umas|e|ou|se|pois|de|em|com|para|por|sem|via
### Romanian:
>un|o|de|din|cu|fără|sau|în|la|pe|peste|ca|pentru|și
### Finnish (Not familiar)
>ja|tai|jos
### Hungarian (Not familiar)
>a|egy|az|ból|ből|tól|től|val|vel|nélkül|vagy|ban|ben|nál|nél|on|en|ön|felett|mint|ért|és
### Turkish (Not familiar)
>bir||ile|sensiz|veya|de|da|üzer|olarak|için|ve
### Arabic / Hebrew
Not supported.  

## Article / Prepositions + ' + Word

For example, "L'Armour de Ma Vie' should not be changed to "L'armour de Ma Vie'.  

>Dell|Degl|Sull|Sugl|Dall|Dagl|All|Agl|Nell|Negl|L|D|N|A|O

## Other Contracted Forms with '

Personal Pronoun：(I|You|He|She|It|We|They)('d|'m|'ll|'ve|'re|'s)

## Fixed Cases

>th|st|nd|rd|feat.

## Roman Numbers

>I|II|III|IV|V|VI|VII|VIII|IX|X|XI|XII|XIII|XIV|XV|XVI|XVII|XVIII|XIX|XX  

## Classical Music Opus

UPPER Case for Classical Music：CSM|BWV|S.|SV|  
Proper Case for Classical Music：Op.|Opus|  
lower Case for Classical Music:  
