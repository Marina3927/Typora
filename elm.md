# elm

**0525**

#### polymorphism 

the ability (in programming) to present the same interface for differing underlying forms (data types).

With polymorphism, each of these classes will have different underlying data. A point shape needs only two co-ordinates (assuming it's in a two-dimensional space of course). A circle needs a center and radius. A square or rectangle needs two co-ordinates for the top left and bottom right corners and (possibly) a rotation. An irregular polygon needs a series of lines.

By making the class responsible for its code as well as its data, you can achieve polymorphism. In this example, every class would have its own `Draw()` function and the client code could simply do: shape.Draw() to get the correct behavior for any shape.

This is in contrast to the old way of doing things in which the code was separate from the data, and you would have had functions such as `drawSquare()` and `drawCircle()`.



Computer.keyboard.down

else

else if

***Writing&Using Functions***

|> evaluate the left side and pass to the right side

partial application

#### Anonymous functions

```elm
 -- \param1 param2 -> --Body
 add 1 2 |> \a > a % 2 == 0
```

#### Main

```elm
main = Html.text 

-- local variable
someFunction param = 
	let
		-- assignment here
		(update a variable is not allowed)
	in
		-- expression here
```



***More On Functions***

#### infix function

Fun_name between parameter

#### prefix function

Fun_name followed by parameters

makePie = slice >> bake (key takeaway)

core package and basic module

***Static Type System***

Primitives type

```elm
-- lists
-- tuples=ordered lists of values
-- records = objects (js), except record field must exist, not null
person =
   { name = "James"
   , age = 42 }
.name person
olderperson = { person | age = 43 }
```

Copy data

#### Union Types

```elm
type SomeType = Type1 | Type2 | Type3
type Result error value
	= Ok value
	| Err error
	
first = List.head []
Nothing : Maybe a
```

like an enumeration of different types

i.e. Maybe, Result deals with null exception and 

#### Pattern Matching

in real, type "\" to continue the next line

```elm
type Msg = Msg1 Int | Msg2 String
msg = Msg2 "James"
cast msg of
		Msg1 num -> 
		Msg2 name -> 
```

High-order function

***Elm Types***

(i.e Java) static type system (not dynamic system)

type declarations

slow compiling

cryptic error messages

runtime errors

#### Roles of complier

transfer Source code -> binary / IL

```elm
import String
--(function)
wordCount = String.words >> List.length
wordCount "legit date"
```

#### Type Annotation

Expressive, restricted, generalized

```elm
List.map : map -> List -> List
```





**0522**

[div](https://package.elm-lang.org/packages/elm-lang/html/latest/Html#div) : List (Attribute msg) -> List (Html msg) -> Html msg

exposing ([sth.]) means to use [sth.] without qualification

Represents a generic container with no special meaning.

```zsh
# Changelog
$ git log --pretty="- %s"
$ git log --pretty=”%s”

# test your code
elm repl
# launch a product
elm reactor
# or
elm-live
## I don't know why I need a playground.
elm install evancz/elm-playground
```

Function/variable: non-capitalized

data type/module name: capitalized

Imperative: C

Object-oriented: C++

Functional-programming: elm

Types of licenses

• Public Domain

*•* Permissive

*•* LGPL - Lesser General Public License

*•* Copyleft

*•* Proprietary

**0518**

Use "wild card" (_) instead of name of unused data.

memory is read-only, no overwrite.

``` c
a++
 // read a; plus 1; store in a
```

**0517**

Elm-core-list

type :exit or  Ctrl + d to exit elm real

MacOS isn’t a Linux OS. What that also means is that instead of shipping with the GNU flavor of command line tools, it ships with the FreeBSD flavor. As such, writing shell scripts which can work across both platforms can sometimes be challenging.

All commands have been installed with the prefix "g".If you need to use these commands with their normal names, youcan add a "gnubin" directory to your PATH from your bashrc like:

PATH="/opt/homebrew/opt/grep/libexec/gnubin:$PATH"

Use Linux pipes to choreograph(compose the sequence of steps and moves 编舞) how command-line utilities collaborate

```zsh
awk '{[pattern] action}' {filenames}   # 行匹配语句 awk '' 只能用单引号
# 每行按空格或TAB分割，输出文本中的1、4项
$ awk '{print $1,$4}' log.txt

awk -F  #-F相当于内置变量FS, 指定分割字符
$ awk -F, '{print $1,$2}' log.txt # field-separator is ','
# 使用多个分隔符.先使用空格分割，然后对分割结果再使用","分割
 $ awk -F '[ ,]'  '{print $1,$2,$5}'   log.txt
 
awk -v  # 设置变量
awk -va=1 '{print $1,$1+a}' log.txt
$ awk -va=1 -vb=s '{print $1,$1+a,$1b}' log.txt
awk -f {awk脚本} {文件名}
```



**0515**

Modularity: WIndow is not modular. 

Reboot a computer

Good: **Linux**, a kernel, in terms of hardware support

VS. **BSD**, stands for “Berkeley Software Distribution,” both a kernel and **an operating system** (distributions), in terms of server

Mint, Manjaro

### Package format

They are used when multiple files — such as those required for the installation of software — need to be distributed. The package is created to combine all the required data files, both pre-compiled binaries, as well as source, text or data files, into a single archive. The packages may also be created for back-up storage and portability

download through package manager

- RPM packages (.rpm)
- Debian packages (.deb)(distros)
- TAR archives (.tar)
- TGZ archives (.tgz)
- GZip Archives (.gz)
- (.msi)

Homebrew is a repository of open source **commands**.

**Interface** channels info.

Finder uses graphical (WIMP) interface.

**Terminal** is a program that can access **CLI**

**Prompt** is the character or characters that the shell presents in the terminal.app to indicate it is waiting for input. BASH shell uses `$` for the prompt character, while ZSH uses `%` for the prompt character

**chmod +x** is a command that adds the **execute permission** to a file for the owner, group, and everyone else. The file can be run as a program.

### Key Combos

time-saving key combos.

- Ctrl + U – delete from the cursor to the start of the line.
- Ctrl + K – delete from the cursor to the end of the line.
- Ctrl + W – delete from the cursor to the start of the preceding word.
- Alt + D – delete from the cursor to the end of the next word.
- Ctrl + L – clear the terminal.

```zsh
$# 是传给脚本的参数个数
$``0` `是脚本本身的名字
$``1` `是传递给该shell脚本的第一个参数
$``2` `是传递给该shell脚本的第二个参数
$@ 是传给脚本的所有参数的列表
$* 是以一个单字符串显示所有向脚本传递的参数，与位置变量不同，参数可超过``9``个
$$ 是脚本运行的当前进程ID号
$? 是显示最后命令的退出状态，``0``表示没有错误，其他表示有错误
```

**0511**

Table of Content; Rules; Tricks and Treats: Scoring; Hints; Console; Game variations

Experience; Mechnical Functions; Environment; Story

CC: overlap & difference

Shell scripting

Bash, shell

**Data Modeling**

```elm
type alias Model = Int
//
type alias Model =
  { content : String
  }
```

Starting with a record makes it easy to add more fields as our app gets more complicated.

**track the current count**

```elm
init : Model
init =
  0
```

INPUT. First UPDATE (MODEL). Then VIEW. New HTML

**view function** takes in Modelm outputs HTML. has a onClick handler

```elm
view : Model -> Html Msg
view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (String.fromInt model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]
// (model = )...
  div []
    [ input [ placeholder "Text to reverse", value model.content, onInput Change ] []
    , div [] [ text (String.reverse model.content) ]
    ]

```

**update function**

> type Msg = Increment | Decrement
>
> ```elm
> update : Msg -> Model -> Model
> update msg model =
>   case msg of
>     Increment ->
>       model + 1
> 
>     Decrement ->
>       model - 1
> // (case msg of)
> Change newContent ->
>       { model | content = newContent }
> ```

### div

The `<div>` tag defines a division or a section in an HTML document.

The `<div>` tag is used as a container for HTML elements - which is then styled with CSS or manipulated with JavaScript.

The `<div>` tag is easily styled by using the class or id attribute.

Any sort of content can be put inside the `<div>` tag! 

**Note:** By default, browsers always place a line break before and after the `<div>`element.

