首先判断专辑艺术家是否为Various Artists
```
$If <Album Artist>="Various Artists"
```
### Album Artist = Various Artists
如果是群星专辑，则文件夹结构如下
```
<Album Artist>\<Year (yyyy)> - <Genre> - $Left(<Album>,70)\
```
#### Various Artists命名规则
对应的文件命名规则如下，首先判断盘数是否为1
```
$If <Disc Count>=1
```
如果为单盘专辑，则文件名不需要显示盘号
```
<Track#> - <Artist> - $Left(<Title>,50)
```
如果为多盘专辑，则文件名需要显示盘号
```
<Disc-Track#> - <Artist> - $Left(<Title>,50)
```

### Album Artist != Various Artists
首先判断Genre Category
```
$If
```

## File Structure
### Root Directory

Check Tag: **Album Artists = Various Artists**

For various artists, create a seperate folder exclusively for this kind of album, either studio album type or complition one, regardless of its genre. 

Check Tag: **Genre = xxxx** 

For genre, divide into four subgroups: classical, early music, ethnic & others. 

### Sub-Directory

Note: The address following "Final Structure" is composed of fixed strings (inside ""), special symbols, musicbee reserved tags and musicbee functions (following $). 

#### 1. Various Artists

Check Tag: **Album Artist = Various Artists**

Final Structure: Year - Genre - Album \ Disc-Track# - Artist - Title

#### 2. Classical
Check Tag: **Genre = Classical or Opera or Vocal**

To define a classical album, there are two important attributes: composers & performers. 

For an album dedicated only to one composer, set both display artist and album artist to the name of composer. Fill the following slots in artist field with performers, original artist with the most important performer of your choice (e.g. the conductor or orchestra for symphony, the vocalist for vocal works).

Final Structure: "Composer" \ Composer \ Original Artist - Year - Album \ Disc-Track# - Title (Limited to 50 characters for Album and Title)

For an album dedicated to multiple composers, set album artist to one desired performer (same as original artist choice in the case above), but display artist to its corresponding composer for each track. For original artist tag, leave it blank.

Final Structure: "Performer" \ Album Artist \ Year - Album \ Disc-Track# - Composer - Title (Limited to 50 characters for Album and Title)

#### 3. Early Music
Check Tag: **Genre = Antique or Medieval or Early Music**

Different from classical genre, there are many tracks in medieval or renaissance period missing info of their composers, hence either anonymous or blank. 

For an album dedicated only to one composer, set both display artist and album artist to the name of composer. Fill the following slots in artist field with performers (usually ensemble), original artist with the most important performer of your choice (usually ensemble).

For an album dedicated to multiple composers, set both display artist and album artist to the name of the chosen performer. Fill the following slots in the artist field with composers and other performers, and original artist same as album artist. 

Final Structure for both cases:  Original Artist \ Year - Album \ Disc-Track# - Title

#### 4. Ethnic
Check Tag: **Genre = Ethnic - xxxx**

#### 5. Others
Check Tag: **Other Genres**

Group the first letter of the album artists and create subfolders for each letter (For Chinese and Japanese characters there are no available practical solutions yet). 

Final Structure: $Group \ Album Artist \ Year - Album \ Disc-Track# - Title
