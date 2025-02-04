
# Requirements
Additional Tagging and Reporting Tool Plugin: [Link](https://getmusicbee.com/addons/plugins/49/additional-tagging-amp-reporting-tools/)

MP3Tag: [Link](https://www.mp3tag.de/en/download.html)

# Sorting of Artists' Names

In order to keep the folders in the music library organized, a sorting rule for artists' names should be created first. 

## Latin Alphabelt / Symbols / Numbers

No change.  

## Chinese / Cantonese

Use either pinyin or their English names. In my case, I choose to use pinyin in this case. 

For example, "林憶蓮" should be sorted as "Lin Yilian" instead of "Sandy Lam". 

## Korean

Use romanization. 

## Japanese / Cyrillic

Use romanization. 

# Folder Structure

## Musicbee Code

```
$If(<Album Artist>="Various Artists",_Various" "Artists\<Year (yyyy)>" - "<Genre>" - "$Left(<Album>,70)\$If(<Disc Count>=1,<Track#>" - "<Artist>" - "$Left(<Title>,50),<Disc-Track#>" - "<Artist>" - "$Left(<Title>,50)),$If(<Genre Category>="Classical",$Group(<Sort Album Artist>,1)\$IsNull(<Original Artist>,<Album Artist>,<Original Artist>)\<Year (yyyy)>" - "$Left(<Album>,70)\$If(<Disc Count>=1,$IsNull(<Composer>,<Track#>" - "$Left(<Title>,70),<Track#>" - "$Split($First(<Composer>)," (",1)" - "$Left(<Title>,70)),$IsNull(<Composer>,<Disc-Track#>" - "$Left(<Title>,70),<Disc-Track#>" - "$Split($First(<Composer>)," (",1)" - "$Left(<Title>,70))),$Group(<Sort Album Artist>,1)\<Album Artist>\<Year (yyyy)>" - "$Left(<Album>,70)\$If(<Disc Count>=1,<Track#>" - "$Left(<Title>,50),<Disc-Track#>" - "$Left(<Title>,50))))  
```

## Stucture Breakdown

# 3

d 