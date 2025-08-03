# Notepad++ Clarion & Clarion Template UDL


![Screenshot](https://github.com/Intelligent-Silicon/Notepad---Clarion---Clarion-Template-UDL/blob/main/TemplateExample1.png)

![Screenshot](https://github.com/Intelligent-Silicon/Notepad---Clarion---Clarion-Template-UDL/blob/main/TemplateExample2.png)

## TLDR

[Clarion Language and Clarion Template Language UDL XML File for importing in NPP.](Clarion%20NPP%20UDL.xml)

Notepad ++, Language, User Defined Language, Define your Language, Import, Select the above XML file.
After the 'Import Successful' message appears, select 'Clarion' from the dropdown list box.

## Summary of Rules
Rule parsing takes place in order of the XML \<Keywords> in the \<KeywordList>.

Ignore Case should be ticked (next to Export). Clarion is not case sensitive.

Folder & Default: Folding in Code 1 Style - Does not need whitespace around the symbol or keyword.

Folder & Default: Folding in Code 2 Style - Needs whitepace around the symbol or keyword.

Operators & Delimiters: Operators 1 Style - Does not need whitepsace around the symbol

Operators & Delimiters: Operators 2 Style - Needs whitepsace around the symbol.

Keywords Lists: Group Prefix Mode - Match anything that starts with the keyword.

Keywords can only be used once - A keyword can only be in one Keywords Lists:group style or Folder & Default:Folding code group style.

Where a keyword exists which is extended, the smallest keyword needs to be last to be parsed last, eg \#AtStart \#AtEnd \#At or \#EndCase and \#End or \#EndIF and \#End

Comment & number:
Decimal Seperator: Both

Prefix 1 & Suffix 2 (first and last) group only used with decimal digits

Prefix 2 works with/can be extended with Extras 1

Extras 2 works with/can be extended with Suffix 1

eg 

[Prefix1][Decimals][Suffix2]

[Prefix2][Extras1] and [Extras2][Suffix1]



For backgrounds to work with White Mode and Dark Mode, the background needs to be Black & Transparent ticked.

If you see a keyword with two colours, this indicates there is a mismatch in the parsing. Identify the rules and rehash them. 

eg \#AtStart where At is one colour, and Start is another

eg \#EndIF where End is one colour and IF is another.

NPP Tokens - ((EOL)) ((WHITESPACE))



## Folder & Default tab

Code 1 Style - Does not need whitespace around the symbol or keyword.

Code 2 Style - Needs whitepace around the the symbol or keyword.

Default style - Orange except for keywords

All Default Style Sample Text is in Orange

### Folding in code 1 Style - Pale Yellow
Template Code Folders - folding on \#Function and its \#End equivalent

Open: 
```
\#Boxed    \#Button     \#Context    \#Default    \#Enable     \#Field      \#GlobalData     \#LocalData      \#Loop       \#Prepare    \#Reports    \#Restrict       \#Section    \#Sheet      \#Tab    \#Windows    \#With       \#AtStart \#AtEnd \#At \#Case       \#IF     \#For    \#Loop       \#Create \#Open
```

Close: 
```
\#EndBoxed \#EndButton  \#EndContext \#EndDefault \#EndEnable  \#EndField   \#EndGlobalData  \#EndLocalData   \#EndLoop    \#EndPrepare \#EndReports \#EndRestrict    \#EndSection \#EndSheet   \#EndTab \#EndWindows \#EndWith    \#EndAt              \#EndCase    \#EndIF  \#EndFor \#EndLoop    \#Close          \#End
```

If you want to fold on the \#Else add it to Middle but this will stop you from folding the entire \#IF \#EndIF structure.
Its a personal choice if this is used or not. This UDL does not use it, but this is how you would do it.

Open: \#If

Middle: \#Else

Close: \#EndIf


Where longer variations of a keyword exist, eg. \#AtStart, \#AtEnd & \#At, the \#At needs to be last because so that the longer versions can be parsed 
and coloured first. If \#At is encountered first, the Start and End of \#AtStart and \#AtEnd will be coloured in the Default style colour.
In the case of \#EndIF \#EndCase \#EndFor and \#End, the \#End needs to be last.

## Keyword Lists
Prefix Mode - Match anything that starts with.
This colours all Template commands not listed in the Folders

Like the examples above with \#At and \#End, the smallest keywords with Prefix mode switched ON like in the of \# and %, these need to be in the last groups.
This way individual keywords coloured differently in the first groups are parsed first and accordingly.

### 1st Group - Turquoise
Clarion words used with templates or in the main language or with Classes.

Taken from the Clarion 11 SoftVelocity.Generator.Resources.ClarionTemplate-Mode.xshd

Add these words to the 1st Group. 
``` clarion
check color component control drop edit embed embedbutton expr field 
format from icon key keycode opendialog optfield option picture procedure 
radio savedialog spin text whenaccepted req default call extract exists 
fileexists fullname inlist instance invoke items linkname quote replace 
seperator slice unquote varexists file at times until for by read where 
hlp section choose multi inline hide adjust not sub instring len and clear 
clarion abc cw20 long unique upper or xor accept break case catch code cycle 
data do else elsif end execute exit finally function goto if loop member new 
of orof parent program return routine self then while as checked defaultof 
foreach getter in is namespace out params ref setter synclock throw tryas 
typeof unchecked using yield application item join map menu menubar module 
ole olecontrol row sheet tab toolbar window event enum indexer property 
struct assert begin compile equate include omit once size any astring 
bfloat4 bfloat8 blob bool bstring byte cstring date decimal double float4 
pdecimal pstring real short signed sreal string time ulong unsigned ushort 
variant cladecimal clalong clastring object class custom detail ellipse 
footer form group header image interface line list project queue record 
report view above absolute alone alrt angle auto autosize ave below bevel 
binary bindable bitmap boxed c cap center centered cnt column com 
compatibility const cursor delay derived dim dll document dock docked down 
dragid driver dropid dup encrypt expand extend external fill filter first 
fix fixed flat font full globalclass gray grid hscroll hvscroll iconize imm 
implements inner ins landscape last late layout length lft linewidth link 
locate mark mask max maximize mdi meta min mm modal msg name nobar nocase 
noframe nomemo nomerge nosheet oem opt order outer over ovr owner page 
pageafter pagebefore palette paper partial pascal password points pre preview 
primary private proc protected range raw readonly reclaim repeat resize 
scroll single smooth spread static std step stretch sum suppress tally 
target thous thread tiled timer tip together toolbox trn up upr use value 
vertical vcr virtual vscroll wallpaper width withnext withprior wizard wrap 
zoom double separator pageno rtf system type autodispose internal netclass 
public null true false priority toolbar
```

### 2nd Group - Lime Green
```
%true %false 
```

### 3rd Group - Pink
Prefix mode = Ticked
These are the Clarion picture tokens. See Comment & Number below for more info.
```
@s @d @n @e @t
```

### 7th Group - Pale Yellow
Prefix mode = Ticked
You could probably get away with just the \#, but as all template \#Commands have to start
with a letter, this enforces that rule.
```
\#a \#b \#c \#d \#e \#f \#g \#h \#i \#j \#k \#l \#m \#n \#o \#p \#q \#r \#s \#t \#u \#v \#w \#x \#y \#z 
```


### 8th Group - Pale Mauve
Prefix mode = Ticked
You could probably get away with just the %, but as all %Symbols have to start
with a letter, this enforces that rule.
```
%a %b %c %d %e %f %g %h %i %j %k %l %m %n %o %p %q %r %s %t %u %v %w %x %y
```

## Comment & Number
Line comment position : Allow anywhere

Allow folding of comments: Ticked

Decimal Seperator: Both

### Comment line style - Lime Green
Open: 
```
\#! \#<!
```
Continue character: <blank>

Close: 
```
\#! \#<!
```

This is a comment
\#<! This is also a comment starting in what ever column specified in \#Comment(50)

### Number Style - Pink
Use lower case letter.

Prefix 1 & Suffix 2 (first and last) only used with decimal digits.

Prefix 2 works with/can be extended with Extras 1.

Extras 2 works with/can be extended with Suffix 1.

Decimal Seperator: Both


### hexadecimal -  0-9 and A-F.
Extras 2: 
```
a b c d e f
```
Suffix 1: 
```
h
```

### binary - 0 or 1
Suffix 1: 
```
b
```

### Octal 0 to 7 
Suffix 1: 
```
o
```

### Clarion Pictures - Pink
Keywords List 
3rd group: - Pink
Prefix mode = Ticked
Clarion picture token prefix and currency symbols
``` 
@s @d @n @e @t £ $ € de fr hk$ د.إ
```

### Clarion Pictures - Pink
Operators & Delimiters
Delimiter 3 - Pink
Open: 
```
@p @k
```
Close: 
```
p k
```

## Operators & Delimiters 
These must be spaced apart otherwise they are treated as a dual or more 
character string eg @\#. This is so that RegEx characters can be "escaped code".

Operators 1 - Pastel Blue BOLD
```
( [ { } ] ) & , | ~ = < > + - / * : ; ?
```

This treats everything inside the Apostrophe's as a string and colours
accordingly.

Delimiter 1 style - Light Green 
Open: 
```
'
```
Escape:
Close: 
```
'
```



