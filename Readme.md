
# Requirements

Additional Tagging and Reporting Tool Plugin: [Link](https://getmusicbee.com/addons/plugins/49/additional-tagging-amp-reporting-tools/)

MP3Tag: [Link](https://www.mp3tag.de/en/download.html)

# Sorting Rules

The first level of folders in the music library is organized by the initial letter of album artists' names.  To keep it organized, sorting rules for both artists' names and album artists' names should be created first.  

Before adding new music to the music library, these sorting rules should be applied first manually, in both MP3Tag and Musicbee itself.  

## Various Artists

If the album artist of an album is "Various Artists", the sorting name remains the same.  

However in the first level of the folder structure, it is organized into a separate folder called "_Various Artists".  

## Latin Letters / Numbers

No change is needed.  

## Symbols (For windows)

If an artist's name contains any special symbols listed below:  

``` text
\  /  :  *  ?  "  <  >  |
```

Replace them with "_" in sorting names. (Musicbee automatically does this in foldernames and filenames)  

All other symbols remain unchanged.  

This rule also applies to any other fields used in filename.  

## Chinese / Cantonese

Use either pinyin or their English names. The key is the consistency.  

In my case, I choose to use pinyin, because many artists from mainland China don't have official English names.

For example, "**林憶蓮**" should be sorted as "**Lin Yilian**" instead of her English name "Sandy Lam".  

## Korean

If a Korean artist's name doesn't contain any Hangul, then no change is needed. For example, "**T-ara**" remains unchanged.  

If a Korean artist's name contains Hangul, then use romanization. For example, "**이정현**" should be sorted as "**Lee Jung-hyun**".  

## Japanese / Greek /  Cyrillic Letters / Hebrew / Vietnamese / Arabic / Thai...  

Use romanization.  

# Folder Structure

## Musicbee Code

``` text
$If(<Album Artist>="Various Artists","_Various Artists"\<Year (yyyy)>" - "<Genre>" - "$Left(<Album>,70)\$If(<Disc Count>=1,<Track#>" - "<Sort Artist>" - "$Left(<Sort Title>,50),<Disc-Track#>" - "<Sort Artist>" - "$Left(<Sort Title>,50)),$If(<Genre Category>="Classical",$Group(<Sort Album Artist>,1)\$IsNull(<Original Artist>,<Sort Album Artist>,<Original Artist>)\<Year (yyyy)>" - "$Left(<Album>,70)\$If(<Disc Count>=1,$IsNull(<Sort Composer>,<Track#>" - "$Left(<Title>,70),<Track#>" - "$Split($First(<Sort Composer>)," (",1)" - "$Left(<Title>,70)),$IsNull(<Sort Composer>,<Disc-Track#>" - "$Left(<Title>,70),<Disc-Track#>" - "$Split($First(<Sort Composer>)," (",1)" - "$Left(<Title>,70))),$Group(<Sort Album Artist>,1)\<Sort Album Artist>\<Year (yyyy)>" - "$Left(<Album>,70)\$If(<Disc Count>=1,<Track#>" - "$Left(<Title>,50),<Disc-Track#>" - "$Left(<Title>,50))))
```

## Stucture Breakdown

### \<Album Artist\> is "Various Artists"

In this case, the first level folder should be named "**_Various Artists**".  

The second level follows "**Year - Genre - Album**" structure:

`<Year (yyyy)>" - "<Genre>" - "$Left(<Album>,70)`

The third and last level depends on the disc number of an album:

if the album only contains one disc, then "**#Track - Artist - Title**":  

`<Track#>" - "<Artist>" - "$Left(<Title>,50)`

otherwise "**#Disc-#Track - Artist - Title**":

`<Disc-Track#>" - "<Artist>" - "$Left(<Title>,50)`

### \<Album Artist\> is not "Various Artists"

#### \<Genre Category\> is "**Classical**"  

For classical music, it is better to use "**Performer**" to differentiate different versions of the same piece.  

In my case, for each track there is a unique "**Performer**" saved in \<**Original Artist**\> field. If a tracks lacks  \<**Original Artist**\>, then it will use  \<**Sort Album Artist**\> instead.  

`$Group(<Sort Album Artist>,1)\$IsNull(<Original Artist>,<Sort Album Artist>,<Original Artist>)\<Year (yyyy)>" - "$Left(<Album>,70)`

Then the final filename will depend on the disc number. And if a track contains at least one composer, the first composer in the tag will be used in the filename.  

`$If(<Disc Count>=1,$IsNull(<Sort Composer>,<Track#>" - "$Left(<Title>,70),<Track#>" - "$Split($First(<Sort Composer>)," (",1)" - "$Left(<Title>,70)),$IsNull(<Sort Composer>,<Disc-Track#>" - "$Left(<Title>,70),<Disc-Track#>" - "$Split($First(<Sort Composer>)," (",1)" - "$Left(<Title>,70)))`  

#### \<Genre Category\> is not "**Classical**"  

Group \<**Sort Album Artist**\> by their initial letters. And then for each album artist, sort their albums by `<Year (yyyy)>" - "$Left(<Album>,70)`

`$Group(<Sort Album Artist>,1)\<Sort Album Artist>\<Year (yyyy)>" - "$Left(<Album>,70)\$If(<Disc Count>=1,<Track#>" - "$Left(<Title>,50),<Disc-Track#>" - "$Left(<Title>,50))))`  