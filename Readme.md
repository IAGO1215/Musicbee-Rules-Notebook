# invinciblemusicbeerules
## Requirements
Additional Tagging and Reporting Tool Plugin: [Link](https://getmusicbee.com/addons/plugins/49/additional-tagging-amp-reporting-tools/)

MP3Tag

## File Structure
### Root Directory
Check Tag: **Genre = xxxx & Album Artists = Various Artists**

For various artists, create a seperate folder exclusively for this kind of album, either studio album type or complition one, regardless of its genre. 

For genre, divide into four subgroups: classical, early music, ethnic & others. 

### Sub-Directory

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

Different from classical genre, many tracks in medieval or early music genre miss their composers info, hence either anonymous or blank. 

For an album dedicated only to one composer, set both display artist and album artist to the name of composer. Fill the following slots in artist field with performers (usually ensemble), original artist with the most important performer of your choice (usually ensemble).

For an album dedicated to multiple composers, set both display artist and album artist to the name of the chosen performer. Fill the following slots in the artist field with composers and other performers, and original artist same as album artist. 

Final Structure for both cases:  Original Artist \ Year - Album \ Disc-Track# - Title

#### 4. Ethnic
Check Tag: **Genre = Ethnic - xxxx**

#### 5. Others
Check Tag: **Other Genres**

Group the first letter of the album artists and create subfolders for each letter (For Chinese and Japanese characters there are no available practical solutions yet). 

Final Structure: Group Letter \ Album Artist \ Year - Album \ Disc-Track# - Title
