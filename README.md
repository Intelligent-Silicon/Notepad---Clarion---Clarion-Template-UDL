# Notepad++ Clarion & Clarion Template UDL


\#! Rule parsing takes place in order of the XML \<Keywords> in the \<KeywordList>.

\#! Altering the order of the <Keywords> could alter the parsing order. Try it!

\#! Ignore Case should be ticked (next to Export).

\#! Code 1 Style - Does not need whitespace around the symbol or keyword.

\#! Code 2 Style - Needs whitepace around the the symbol or keyword.

\#! Operators 1 Style - Does not need whitepsace around the symbol

\#! Operators 2 Style -Needs whitepsace around the symbol.

\#! Prefix Mode - Match anything that starts with.

\#! Keywords can only be in one Keyword style group or Folder style group.

\#! Keywords can only be used once.

\#! For backgrounds to work with White Mode and Dark Mode, the background needs to be Transparent.

\#! If you see a keyword with two colours, this indicates there is a mismatch
\#! in the parsing. Identify the rules and rehash them. 

\#! eg \#AtStart where At is one colour, and Start is another

\#! eg \#EndIF where End is one colour and IF is another.

\#! NPP Tokens - ((EOL)) ((WHITESPACE))

\#! Folder & Default tab

\#! Code 1 Style - Does not need whitespace around the symbol or keyword.

\#! Code 2 Style - Needs whitepace around the the symbol or keyword.

\#! Default style - Orange except for keywords

All Default Style Sample Text is in Orange

\#! Folding in code 1 Style - Pale Yellow

\#! Template Code Folders - folding on \#Function and its \#End equivalent

\#!

\#! Open:  \#Boxed    \#Button     \#Context    \#Default    \#Enable     \#Field      \#GlobalData     \#LocalData      \#Loop       \#Prepare    \#Reports    \#Restrict       \#Section    \#Sheet      \#Tab    \#Windows    \#With       \#AtStart \#AtEnd \#At \#Case       \#IF     \#For    \#Loop       \#Create \#Open

\#! Close: \#EndBoxed \#EndButton  \#EndContext \#EndDefault \#EndEnable  \#EndField   \#EndGlobalData  \#EndLocalData   \#EndLoop    \#EndPrepare \#EndReports \#EndRestrict    \#EndSection \#EndSheet   \#EndTab \#EndWindows \#EndWith    \#EndAt              \#EndCase    \#EndIF  \#EndFor \#EndLoop    \#Close          \#End

\#IF('This Wraps all of them together')

\#Case(%Symbol[%Cnt])            \#! \#Open: \#Case

\#OF(%Symbol) \#OROF(%Symbol)

\#!

\#OF(%Symbol)

\#!

\#Else

\#!

\#EndCase                        \#! Close: \#EndCase

\#Boxed

\#!

\#EndBoxed

\#Button
\#!
\#EndButton

\#Context
\#!
\#EndContext

\#Default
\#!
\#EndDefault

\#Enable
\#!
\#EndEnable

\#Field
\#!
\#EndField

\#GlobalData
\#!
\#EndGlobalData

\#LocalData
\#!
\#EndLocalData

\#Loop
\#!
\#EndLoop

\#Reports
\#!
\#EndReports

\#Restrict
\#!
\#EndRestrict

\#Section
\#!
\#EndSection

\#Sheet
\#!
\#EndSheet

\#Tab
\#!
\#EndTab

\#Windows
\#!
\#EndWindows

\#With
\#!
\#EndWith

\#AtStart
\#!
\#EndAt

\#AtEnd
\#!
\#EndAt

\#At
\#!
\#EndAt

\#Case
\#OF(%symbol)
\#!
\#OROF(%symbol)
\#!
\#Else
\#!
\#EndCase

\#Case
\#OF(%symbol)
\#!
\#OROF(%symbol)
\#!
\#Else
\#!
\#End

\#IF(%Symbol)
\#!
\#ElsIF(%Symbol)
\#!
\#Else
\#!
\#EndIF

\#IF(%Symbol)
\#!
\#ElsIF(%Symbol)
\#!
\#Else
\#!
\#End

\#For(%Symbol)
\#!
\#EndFor

\#For(%Symbol)
\#!
\#End

\#Loop,times
\#!
\#EndLoop

\#Loop,times(9)
\#!
\#End

\#Loop,until(%Symbol = %true)
\#!
\#Endloop

\#Loop,for(%cnt,%start,%end),by(%step)
\#!
\#Endloop


\#Create(%file)
\#!
\#Close

\#Open(%File),Read
\#!
\#Close

\#EndIF \#! End of the IF Wrap


\#! Folding in code 1 Style - Pale Yellow
\#If(%True)                      \#! Open: \#If
\#! If Example
\#Else
\#! Else
\#EndIF                          \#! Close: \#EndIf

\#! Folding in code 1 Style - Pale Yellow
\#! If you want to fold on the \#Else add it to Middle but this
\#! will stop you from folding the entire \#IF \#EndIF structure.
\#! Its a personal choice if this is used or not.
\#! This UDL does not use it.
\#If(%True)                      \#! Open: \#If
\#! If Example
\#Else                           \#! Middle: \#Else
\#! Else
\#EndIF                          \#! Close: \#EndIf

\#! Folding in code 1 Style - Pale Yellow
\#Loop                           \#! Open: \#Loop
    \#IF(%Condition = %True)
        \#Break
    \#EndIF
\#EndLoop                        \#! Close: \#EndLoop

\#! Folding in code 1 Style - Pale Yellow
\#Sheet                          \#! Open: \#Sheet
\#!
\#EndSheet                       \#! Close: \#EndSheet

\#! Folding in code 1 Style - Pale Yellow
\#Tab                            \#! Open: \#Tab
\#!
\#EndTab                         \#! Close: \#EndTab

\#! Folding in code 1 Style - Pale Yellow
\#Prepare                        \#! Open: \#Prepare
\#!
\#EndPrepare                     \#! Close: \#EndPrepare

\#! Folding in code 1 Style - Pale Yellow
\#Button                         \#! Open: \#Button
\#!
\#EndButton                      \#! Close: \#EndButton


\#! In this example there are 3 template keywords: \#AtStart, \#AtEnd & \#At
\#! The \#At needs to be last because so that the longer versions can be parsed 
\#! and coloured first. If \#At is encountered first, the Start and End of \#AtStart 
\#! and \#AtEnd will be coloured in the Default style colour.


\#! Folding in code 1 Style - Pale Yellow
\#AtStart                        \#! Open: \#AtStart
\#!
\#EndAt                          \#! Close: \#EndAt - Only list this once 

\#! Folding in code 1 Style - Pale Yellow
\#AtEnd                          \#! Open: \#AtEnd - Default Style bug colours 'END'
\#!
\#EndAt                          \#! Close: \#EndAt - Only list this once

\#! Folding in code 1 Style - Pale Yellow
\#At                             \#! Open: \#At
\#!
\#EndAt                          \#! Close: \#EndAt


\#! In this example there two template keywords: \#EndIF \#EndCase \#EndFor and \#End.
\#! Like the \#AT example above, the shortest word needs to be last, so \#End 
\#! always needs to be last otherwise the IF in \#EndIf will be coloured by the 
\#! default style. Add the \#End to the front of the Close: box to see the 
\#! wrong colouring.
 
\#If                             \#! Open: \#IF
\#!
\#EndIF                          \#! Close: \#EndIF

\#If                             \#! Open: \#If
\#!
\#End                            \#! Close: \#End

\#! Keyword Lists
\#! Prefix Mode - Match anything that starts with.
\#! This colours all Template commands not listed in the Folders

\#! Like the examples above with \#At and \#End, the smallest keywords with Prefix
\#! mode switched on for the case of \# and %, need to be last.
\#! This way individual keywords coloured differently in the first groups are
\#! parsed accordingly.
\#! eg if \#Accept is in a keyword group before \# which is in the 7th Group, and
\#! they have different colours, the \#Accept will show the correct colour and
\#! so will all other words prefixed with \#

\#! 1st Group - Turquoise
\#! Colour the CHECK in this prompt, add the word CHECK to one of the groups
\#! and colour accordingly. It will colour the word Check in the \#Prompt below.
\#! If you see a keyword with two colours, this indicates there is a mismatch
\#! in the parsing. Identify the rules and rehash them.
\#!
\#! Largest words first, eg FileExists before File
\#!
\#! Template \#Prompt/\#Set Keywords:
\#! Taken from the Clarion 11 XML 
\#! SoftVelocity.Generator.Resources.ClarionTemplate-Mode.xshd

\#! check color component control drop edit embed embedbutton expr field 
\#! format from icon key keycode opendialog optfield option picture procedure 
\#! radio savedialog spin text whenaccepted req default call extract exists 
\#! fileexists fullname inlist instance invoke items linkname quote replace 
\#! seperator slice unquote varexists file at times until for by read where 
\#! hlp section choose multi inline hide adjust not sub instring len and clear 
\#! clarion abc cw20 long unique upper or xor accept break case catch code cycle 
\#! data do else elsif end execute exit finally function goto if loop member new 
\#! of orof parent program return routine self then while as checked defaultof 
\#! foreach getter in is namespace out params ref setter synclock throw tryas 
\#! typeof unchecked using yield application item join map menu menubar module 
\#! ole olecontrol row sheet tab toolbar window event enum indexer property 
\#! struct assert begin compile equate include omit once size any astring 
\#! bfloat4 bfloat8 blob bool bstring byte cstring date decimal double float4 
\#! pdecimal pstring real short signed sreal string time ulong unsigned ushort 
\#! variant cladecimal clalong clastring object class custom detail ellipse 
\#! footer form group header image interface line list project queue record 
\#! report view above absolute alone alrt angle auto autosize ave below bevel 
\#! binary bindable bitmap boxed c cap center centered cnt column com 
\#! compatibility const cursor delay derived dim dll document dock docked down 
\#! dragid driver dropid dup encrypt expand extend external fill filter first 
\#! fix fixed flat font full globalclass gray grid hscroll hvscroll iconize imm 
\#! implements inner ins landscape last late layout length lft linewidth link 
\#! locate mark mask max maximize mdi meta min mm modal msg name nobar nocase 
\#! noframe nomemo nomerge nosheet oem opt order outer over ovr owner page 
\#! pageafter pagebefore palette paper partial pascal password points pre preview 
\#! primary private proc protected range raw readonly reclaim repeat resize 
\#! scroll single smooth spread static std step stretch sum suppress tally 
\#! target thous thread tiled timer tip together toolbox trn up upr use value 
\#! vertical vcr virtual vscroll wallpaper width withnext withprior wizard wrap 
\#! zoom double separator pageno rtf system type autodispose internal netclass 
\#! public null true false priority toolbar

\#PROMPT('Prompt Text',CHECK),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',Procedure),%Symbol,At(10),Default(%false)
\#PROMPT('Prompt Text',Option),%Symbol,At(10),Default(1)
\#PROMPT('Prompt Text',Radio),%Symbol,At(10),Default(0),WhenAccepted(%grpDoSomething())
\#Validate(%grpDoSomething,%param1, %param2,'Message to display when False')


\#! 2nd Group - Lime Green
\#! %true %false am pm

\#PROMPT('Prompt Text',CHECK),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',Procedure),%Symbol,At(10),Default(%False)
\#PROMPT('Prompt Text',CHECK),%Symbol,At(10),Default(1)
\#PROMPT('Prompt Text',Procedure),%Symbol,At(10),Default(0)

\#! 3rd Group - Pink
\#! Prefix mode = Ticked
\#! These are the Clarion picture tokens. See Comment & Number below for more info.
\#! @s @d @n @e @t


\#! 7th Group - Pale Yellow
\#! Prefix mode = Ticked
\#! You could probably get away with just the \#, but as all \#Commands have to start
\#! with a letter, this enforces that rule.

\#! \#a \#b \#c \#d \#e \#f \#g \#h \#i \#j \#k \#l \#m \#n \#o \#p \#q \#r \#s \#t \#u \#v \#w \#x \#y \#z 

\#a \#b \#c \#d \#e \#f \#g \#h \#i \#j \#k \#l \#m \#n \#o \#p \#q \#r \#s \#t \#u \#v \#w \#x \#y \#z 

\#! This colours all Template symbols not listed in the Folders
\#! 8th Group - Pale Mauve
\#! Prefix mode = Ticked
\#! You could probably get away with just the %, but as all \#Symbols have to start
\#! with a letter, this enforces that rule.

\#! %a %b %c %d %e %f %g %h %i %j %k %l %m %n %o %p %q %r %s %t %u %v %w %x %y

%a %b %c %d %e %f %g %h %i %j %k %l %m %n %o %p %q %r %s %t %u %v %w %x %y

\#! Comment & Number
\#! Line comment position : Allow anywhere
\#! Allow folding of comments: Ticked
\#!
\#! Comment line style
\#! Open: \#! \#<!
\#! Continue character:
\#! Close: \#! \#<!

\#! This is a comment
\#<! This is also a comment starting in what ever column specified in \#Comment(50)

\#! Number Style - Pink
\#! Use lower case letters, create an Upper case and lower case example, and 
\#! toggle the Ignore Case tick box. If the rules are correct the Upper case
\#! example will use the Default style orange.
\#!
\#! Prefix 1 & Suffix 2 (first and last) only used with decimal digits
\#! Prefix 2 works with/can be extended with Extras 1
\#! Extras 2 works with/can be extended with Suffix 1
\#! eg Prefix 2 & Extras 1 and Extras 2 & Suffix 1
\#! Decimal Seperator: Both


\#! hexadecimal -  0-9 and A-F.
\#! Extras 2: a b c d e f
\#! Suffix 1: h 
\#Equate(0cd1f74fh)
\#Equate(-0cd1f74fh)
\#Equate(0CD1F74FH)      \#! This works if Ignore Case is ticked or 
\#Equate(-0CD1F74FH)     \#! capital H is added to suffix 1

\#! binary - 0 or 1
\#! Suffix 1: b
\#Equate(1000110b)
\#Equate(-1000110b)
\#Equate(1000110B)       \#! This works if Ignore Case is ticked or
\#Equate(-1000110B)      \#! capital B is added to suffix 1

\#! Octal 0 to 7 
\#! Suffix 1: o
\#Equate(7041312o)
\#Equate(-7041312o)
\#Equate(7041312O)       \#! This works if Ignore Case is ticked or
\#Equate(-7041312O)      \#! capital O is added to suffix 1

\#! Clarion Pictures - Pink
\#! Keywords List 
\#! 3rd group: - Pink
\#! Prefix mode = Ticked
\#! Clarion picture token prefix and currency symbols 
\#! @s @d @n @e @t £ $ € de fr hk$ د.إ
\#PROMPT('Prompt Text',@s255),%Symbol,At(10),Default(%True)

\#PROMPT('Prompt Text',@d1),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@d1>40),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@d01>40),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@d01.),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@d01-),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@d01_),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@d01`),%Symbol,At(10),Default(%True)

\#PROMPT('Prompt Text',@n09),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@n13.2),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@n~£~13.2),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@n~£~-13.2),%Symbol,At(10),Default(%True)

\#PROMPT('Prompt Text',@E9.0),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@e12.1),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@E12.1b),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@e12.1),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@E12.1),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@e15_.4),%Symbol,At(10),Default(%True)

\#PROMPT('Prompt Text',@t1),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@t01),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@t01.),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@t01-),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@t01_),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@t01`),%Symbol,At(10),Default(%True)

\#! Clarion Pictures - Pink
\#! Operators & Delimiters
\#! Delimiter 3 - Pink
\#! Open: @p @k
\#! Close: p k

\#PROMPT('Prompt Text',@p\#\#\#-\#\#-\#\#\#\#p),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text', @P<\#/\#\#/\#\#P ),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text', @p(\#\#\#)\#\#\#-\#\#\#\#p),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@P\#\#\#/\#\#\#-\#\#\#\#Pb ),%Symbol,At(10),Default(%True) \#! Trips up here
\#PROMPT('Prompt Text',@p<\#:\#\#PMp ),%Symbol,At(10),Default(%True)   \#! Trips up here
\#PROMPT('Prompt Text', @P<\#' <\#"P ),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text', @P<\#lb. <\#oz.P ),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text', @P4\#\#A-\#P ),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@PA\#\#.C\#P),%Symbol,At(10),Default(%True)

\#PROMPT('Prompt Text',@K\#\#\#-\#\#-\#\#\#\#K),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text', @K\#\#\#\#\#|-\#\#\#\#K ),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text', @K(\#\#\#)@@@-\#\#\@\#\#K),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@K\#\#\#/?\#\#-\#\#\#\#K ),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@k<\#:\#\#^Mk),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text', @K<\#' <\#"K ),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@K4\#_\#A-\#K ),%Symbol,At(10),Default(%True)






\#! Operators & Delimiters 
\#! These must be spaced apart otherwise they are treated as a dual or more 
\#! character string eg @\#. This is so that RegEx characters can be "escaped code".
\#!
\#! Operators 1 - Pastel Blue BOLD
\#! ( [ { } ] ) & , | ~ = < > + - / *
\#! &<>~!@^*-+=|\\#/{}[]:;" ,	.?

( [ { } ] ) & , | ~ = < > + - / *

\#! This treats everything inside the Apostrophe's as a string and colours
\#! accordingly.

\#! Delimiter 1 style - Light Green 
\#! Open: '
\#! Escape:
\#! Close: '

\#! 'Prompt Text' and 'Some Text Here' demonstrate this.

\#PROMPT('Prompt Text',@p\#\#\#-\#\#-\#\#\#\#p),%Symbol,At(10),Default(%True)
\#PROMPT('Prompt Text',@s255),%Symbol,At(10),Default('Some Text Here')




