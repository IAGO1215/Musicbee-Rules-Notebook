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
>A|An|The|Of|From|With|Without|Or|In|At|On|Over|As|For|And
### Italian
>Il|La|Lo|I|Le|Gli|Di|Del|Della|Delle|Dello|Da|Dal|Dalla|Dalle|Dallo|Con|Col|Senza|O|In|Nel|Nella|Nelle|Nello|Sopra|Sotto|Su|Sul|Sulla|Sulle|Sullo|A|Al|Alla|Alle|Allo|Per|Ad
### French
>Le|La|Les|Des|Du|Au|À|En|De|Pour|Sans|Avec|Sur|Sous|Par|Vers
### Spanish
>El|La|Los|Las|De|Del|Por|Para|Y|O|In|I|Al|Con|Sin
### Russian
>И|Или|Либо|В|На|Из|С|От|К|О|Об|Для|Без|По|Про|Через|Под|Над|При|Мимо|Вокруг|Среди|После|До|Во|Пока|У
### German (Generally should be prevented from case conversion due to initial letters of nouns in German are always in upper case)
>ein|eine|einen|einem|einer|eines|der|die|das|dem|den|des|von|vom|zu|zur|zum|ans|aufs|aus|mit|ohne|oder|in|bei|auf|über|als|für|und
### Greek
>Ο|Του|Τον|Οι|Των|Τους|Η|Της|Την|Οι|Τις|Το|Τα|Και|Ή|Αν|Σε|Από|Με|Για|Μετά|Πριν|Με|Χωρίς|Περί|Κατά|Από|Πάνω|Κάτω|Στο|Γύρω|Ανάμεσα|Εκτός|Δίπλα|Για|Ένας|Ενός|Έναν|Ενών|Έναν|Μία|Μίας|Ένα|Στα|Κι|Στο|Στον|Αν|Στη|Στις
### Latin
>Ab|Ad|Cum|De|Ex|In|Inter|Per|Pro|Sine|Sub|Et|Aut|Sed|Nec|Neque|Si|Quia|Ut|Dum|Nam
### Danish\Norwegian\Swedish\Icelandic
>Den|Det|De|En|Et|En|Ett|A|An|I|På|Af|Til|Med|Fra|Om|Over|Under|Ved|Og|Eller|Men|Så|Fordi|Hvis|At|Av|Från|Över|Vid|Och|Att|För|Í|Á|Frá|Til|Með|Um|Undir|Yfir|Við|Eða|Svo|Því|Ef|Að
### Portuguese
>O|A|Os|As|Um|Uma|Uns|Umas|E|Ou|Se|Pois|De|Em|Com|Para|Por|Sem|Via
### Romanian:
>Un|O|De|Din|Cu|Fără|Sau|În|La|Pe|Peste|Ca|Și
### Finnish (Not familiar)
>Ja|Tai|Jos
### Hungarian (Not familiar)
>A|Egy|Az|Ból|Ből|Tól|Től|Val|Vel|Nélkül|Vagy|Ban|Ben|Nál|Nél|On|En|Ön|Felett|Mint|Ért|És
### Turkish (Not familiar)
>Bir|İle|Sensiz|Veya|De|Da|Üzer|Olarak|İçin|Ve
### Arabic / Hebrew
Not supported.  

## Article / Prepositions + ' + Word

For example, "L'Armour de Ma Vie' should not be changed to "L'armour de Ma Vie'.  

>Dell|Degl|Sull|Sugl|Dall|Dagl|All|Agl|Nell|Negl|L|D|N|A|O

## Other Contracted Forms with '

Personal Pronoun  

>(I|You|He|She|It|We|They)('d|'m|'ll|'ve|'re|'s)

## Fixed Cases

>th|st|nd|rd|feat.

## Roman Numbers

>I|II|III|IV|V|VI|VII|VIII|IX|X|XI|XII|XIII|XIV|XV|XVI|XVII|XVIII|XIX|XX  

## Classical Music Opus

UPPER Case for Classical Music：
>CSM|BWV|S.|SV|  
Proper Case for Classical Music：
>Op.|Opus|  
lower Case for Classical Music:  
