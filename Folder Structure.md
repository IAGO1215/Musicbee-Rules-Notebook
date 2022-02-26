首先判断专辑艺术家是否为Various Artists
```
$If<Album Artist>="Various Artists"
```
## Album Artist = Various Artists
如果是群星专辑，则文件夹结构如下
```
_Various Artists\<Year (yyyy)> - <Genre> - $Left(<Album>,70)\
```
#### Various Artists文件命名规则

首先判断盘数是否为1
```
$If<Disc Count>=1
```
如果为单盘专辑，则文件名不需要显示盘号
```
<Track#> - <Artist> - $Left(<Title>,50)
```
如果为多盘专辑，则文件名需要显示盘号
```
<Disc-Track#> - <Artist> - $Left(<Title>,50)
```

## Album Artist != Various Artists
首先判断Genre Category
```
$If<Genre Category> = "Classical"
```
### 古典类
如果是古典类的专辑，文件夹结构如下
```
$Group($Sort(<Original Artist>),1)\<Year (yyyy)> - $Left(<Album>,70)\
```
#### 古典类文件命名规则
首先判断盘数是否为1
```
$If<Disc Count>=1
```
如果为单盘专辑，则文件名不需要显示盘号
```
<Track#> - <Composer> - $Left(<Title>,70)
```
如果为多盘专辑，则文件名需要显示盘号
```
<Disc-Track#> - <Composer> - $Left(<Title>,70)
```

### 早期音乐类
内嵌判断语句
```
$If<Genre Category> = "Early Music"
```
文件夹结构如下
```
$Group($Sort(<Album Artist>),1)\<Year (yyyy)> - $Left(<Album>,70)\
```
#### 早期音乐类文件命名规则
首先判断盘数是否为1
```
$If<Disc Count>=1
```
如果为单盘专辑，则文件名不需要显示盘号；此外，需要判断是否有作曲家信息，如果有，需要在文件名注明，因此需要进一步嵌套判断语句
```
$isNull<Composer>
```
如果没有作曲家信息，则文件名如下
```
<Track#> - $Left(<Title>,50)
```
如果有作曲家信息，则文件名如下（作曲家信息只保留名字部分，名字后括号内的生卒日期无需展示）
```
<Track#> - $Trim($Rsplit($Split(<Composer>,"(",1)," ",1)) - $Left(<Title>,50)
```

如果为多盘专辑，则文件名需要显示盘号；此外，需要判断是否有作曲家信息，如果有，需要在文件名注明，因此需要进一步嵌套判断语句
```
$isNull<Composer>
```
如果没有作曲家信息，则文件名如下
```
<Disc-Track#> - $Left(<Title>,50)
```
如果有作曲家信息，则文件名如下
```
<Disc-Track#> - $Trim($Rsplit($Split(<Composer>,"(",1)," ",1)) - $Left(<Title>,50)
```

### 原声带类
内嵌判断语句
```
$If<Genre Category> = "Soundtrack"
```
文件夹结构如下
```
$Group($Sort(<Album Artist>),1)\<Year (yyyy)> - $Left(<Album>,50) Soundtrack\
```

#### 原声带类命名规则
首先判断盘数是否为1
```
$If<Disc Count>=1
```
如果为单盘专辑，则文件名不需要显示盘号；此外，需要判断曲目的艺术家是否为专辑艺术家，如果不是，需要在文件名注明，因此需要进一步嵌套判断语句
```
$If<Artist>=<Album Artist>
```
如果曲目艺术家与专辑艺术家相同，则文件名如下
```
<Track#> - $Left(<Title>,50)
```
如果曲目艺术家与专辑艺术家不同，则文件名如下
```
<Track#> - <Artist> - $Left(<Title>,50)
```

如果为多盘专辑，则文件名需要显示盘号；此外，需要判断曲目的艺术家是否为专辑艺术家，如果不是，需要在文件名注明，因此需要进一步嵌套判断语句
```
$If<Artist>=<Album Artist>
```
如果曲目艺术家与专辑艺术家相同，则文件名如下
```
<Disc-Track#> - $Left(<Title>,50)
```
如果曲目艺术家与专辑艺术家不同，则文件名如下
```
<Disc-Track#> - <Artist> - $Left(<Title>,50)
```

### 其他类（流行、民谣、金属、黑暗、传统、世界、民乐）
文件夹结构如下
```
$Group($Sort(<Album Artist>),1)\<Year (yyyy)> - $Left(<Album>,50)\
```

#### 其他类文件命名规则
首先判断盘数是否为1
```
$If<Disc Count>=1
```
如果为单盘专辑，则文件名不需要显示盘号；此外，需要判断曲目的艺术家是否为专辑艺术家，如果不是，需要在文件名注明，因此需要进一步嵌套判断语句
```
$If<Artist>=<Album Artist>
```
如果曲目艺术家与专辑艺术家相同，则文件名如下
```
<Track#> - $Left(<Title>,50)
```
如果曲目艺术家与专辑艺术家不同，则文件名如下
```
<Track#> - <Artist> - $Left(<Title>,50)
```

如果为多盘专辑，则文件名需要显示盘号；此外，需要判断曲目的艺术家是否为专辑艺术家，如果不是，需要在文件名注明，因此需要进一步嵌套判断语句
```
$If<Artist>=<Album Artist>
```
如果曲目艺术家与专辑艺术家相同，则文件名如下
```
<Disc-Track#> - $Left(<Title>,50)
```
如果曲目艺术家与专辑艺术家不同，则文件名如下
```
<Disc-Track#> - <Artist> - $Left(<Title>,50)
