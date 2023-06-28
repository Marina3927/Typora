# elm

#### MakeFile

```zsh
# all:
	mkdir -p build
	elm make src/Main.elm --output=build/main.js
	cp -f public/index.html .
	cp -f public/style.css build/style.css
	cp -f public/*.js build/
# format:
	elm-format src/ --yes
# clean:
	rm -rf build/
elmformat *
```

**0612**

Front-end web development: JavaScript (along with [HTML](https://www.codecademy.com/resources/blog/what-is-html/?utm_source=ccblog&utm_medium=ccblog&utm_campaign=ccblog&utm_content=what_is_javascript_used_for_blog) and [CSS](https://www.codecademy.com/learn/learn-css?utm_source=ccblog&utm_medium=ccblog&utm_campaign=ccblog&utm_content=what_is_javascript_used_for_blog)) 

Back-end web (server-side) development: [Node.js](https://www.codecademy.com/learn/learn-node-js?utm_source=ccblog&utm_medium=ccblog&utm_campaign=ccblog&utm_content=what_is_javascript_used_for_blog) (a JavaScript framework)

Mobile, VR, AI



**0605**

```elm
polyFun x y fct = fct x y
-- <function> : a -> b -> ( a -> b -> c ) -> c
-- ( a -> b -> c ) is fct
-- polymorphism

```

**0604**

```elm
removeTail : List a -> List a
removeTail body =
    body
        |> List.reverse
        |> List.tail
        |> Maybe.withDefault []
        |> List.reverse
```

lose of intent
Mislead, boolean is inconsistent
complexity with branching logic (lose single responsibility)
pull us away from friendly domain abstract
API should be written to make it easier for the caller
String: primitive obsession (wild match)
? represent a finit domain
only handle valid constructor
delegate responsibility to...; become a collaborator
Boolean Blindness: lose info -> backtrack, retrieve the dog (Dict.get) ; may not know the time
option let us see; option type
Maybe
Result: minimize the result of boolean branching
Union Types: enforce constraints thanks to type check

**0530**

```zsh
pip3 install -i https://pypi.python.org/simple -U "elm-messenger>=0.2.4"
elm-format /src
```

Scene

layer

component





```elm
1::[2,3,4]
(::) 1 [2,3,4]
-- 2 ways to initialize a model
{ x = 0, y = 0, time = 0, color = Color 5 5 5 }
```

**0529**

*API（Application Programming Interface,[应用程序](https://link.zhihu.com/?target=http%3A//baike.baidu.com/item/%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F)编程接口）是一些预先定义的[函数](https://link.zhihu.com/?target=http%3A//baike.baidu.com/item/%E5%87%BD%E6%95%B0)，目的是提供[应用程序](https://link.zhihu.com/?target=http%3A//baike.baidu.com/item/%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F)与开发人员基于某[软件](https://link.zhihu.com/?target=http%3A//baike.baidu.com/item/%E8%BD%AF%E4%BB%B6)或硬件得以访问一组[例程](https://link.zhihu.com/?target=http%3A//baike.baidu.com/item/%E4%BE%8B%E7%A8%8B)的能力，而又无需访问源码，或理解内部工作[机制](https://link.zhihu.com/?target=http%3A//baike.baidu.com/item/%E6%9C%BA%E5%88%B6)的细节*

修改函数，上位函数随之变化

```elm
-- f1 (f2 para)
-- para
-- |> f2
-- |> f1
List.take
List.drop
-- take/drop the first n members of a list
List.tail
-- extract the rest of the list
List.concatMap
-- Map a given function onto a list and flatten the resulting lists.

-- the location of pipe is appended
```

**0528**

```elm
type Msg
    = GotText (Result Http.Error String)
fetchText : Cmd Msg
fetchText =
	Http.send GotText <| Http.getString "https://example.com/text"

```



**0527**

- `Renderable` is a type alias for a function that takes a `Settings` record and returns a list of shapes.
- `Settings` is a record that contains information about how to render the shapes.
- `group` is a function that takes a list of shapes and returns a single shape that is the group of all the shapes.
- `rect` is a function that takes two integers for width and height, and returns a shape representing a rectangle.
- `fill` is a function that takes a color and a shape, and returns the shape filled with the color.
- `shapes` is a module that contains functions for creating various shapes.
- `subscriptions` are a way that an Elm application can receive external inputs like keyboard events, timer events and WebSocket events, output by a JavaScript library

[`Html.Msg` is used for messages that are sent from the view layer to the update function, while `Msg` ... sent from the update function to the view layer](https://stackoverflow.com/questions/31349125/what-is-the-difference-between-django-html-message-and-message-in-send-mail)[1](https://stackoverflow.com/questions/31349125/what-is-the-difference-between-django-html-message-and-message-in-send-mail)

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

*example*

```elm
> type Action = AddPlayer | Score
> action = AddPlayer
AddPlayer : Repl.Action
> type Action = AddPlayer String | Score Int Int
> AddPlayer
«function> : String -> Repl.Action
> Score
«function> : Int -> Int -> Repl. Action
> action = AddPlayer "James"
AddPlayer "James" : Repl. Action
> msg = AddPlayer "James"
AddPlayer "James" : Repl. Action
> case msg of \
AddPlayer name -> "Add player " ++ name \
Score id points -> "Player id " ++ (toString id) ++ " scored " ++ (toString points)

> first = List.head []
Nothing: Maybe.Maybe a
> case first of \
Just val -> val
Nothing -> "Empty"
"Empty" : String
> import Date
someDate = Date.fromString "01/01/1974"
Ok {} : Result. Result String Date.Date
> case someDate of \
Ok val -> "It was a legit date" \
Err err -> err
"It was a legit date" : String
> someDate = Date.fromString "Not a Date"
Err "unable to parse 'Not a Date' as a date" : Result.Result String Date. Date
> first = List. head []
Nothing: Maybe.Maybe a
Maybe.withDefault "Some Default, because first is Nothing!" first
"Some Default, because first is Nothing!" : String
```

#### Simple app

##### Model

can be a String, or a record:

```elm
type alias Model =
    { meal : List String
    , date : Date
    }
```

##### Update

Input Msg and Model, return Model

##### View

pass the current model and return html (which can generate text)

Functions like div, p, hr, pre, block quote, corresponds to tags in html

```elm
tagName
		: List (Attribute msg)
		--id, class...
		-> List (Html msg)
		--text, div, p
```

​           

**0526**

```zsh
sudo npm --force i -g elm elm-format elm-live
```



**0525**

#### polymorphism 

the ability (in programming) to present the same interface for differing underlying forms (data types).

With polymorphism, each of these classes will have different underlying data. A point shape needs only two co-ordinates (assuming it's in a two-dimensional space of course). A circle needs a center and radius. A square or rectangle needs two co-ordinates for the top left and bottom right corners and (possibly) a rotation. An irregular polygon needs a series of lines.

By making the class responsible for its code as well as its data, you can achieve polymorphism. In this example, every class would have its own `Draw()` function and the client code could simply do: shape.Draw() to get the correct behavior for any shape.

This is in contrast to the old way of doing things in which the code was separate from the data, and you would have had functions such as `drawSquare()` and `drawCircle()`.

```elm
Computer.keyboard.down
else | else if
```

#### (stop-motion video) Creative Title, Pitch Diagram, Instructional Booklet, Cohesive Design

ppt should be created in latex with vector graphics

pitch diagram: High Concept | Experience | Assets | Game Play | Story | Technical Assets | Marketing

experience driven name | high concept driven name

specialty of breaking bricks: Color scheme | Brick shape | Paddle size | Paddle speed | ...

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

