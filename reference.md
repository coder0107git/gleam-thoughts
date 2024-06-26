# Gleam Reference

> [!WARNING]  
> This is still, very, *very*, WIP. Some information is probably incorrect and there are many places that could use better wording.


<!-- TODO: Dynamic table of contents here -->
<!-- TODO: Use the following quote from Lewis somewhere "As our hero lambdaman says: object oriented programming is well named because if someone says you should use it then you should object" -->


## When should I use Gleam?
Whenever or wherever you'd use BEAM or Javascript.


## Is Gleam Imperitive?
Gleam is a functional programing language.


## Does Gleam Have A REPL?
Gleam does not have a REPL right now. It is a higly desired feature though so it will probably be added sometime in the future. If you'd like to work on this just ask what the status of this is. 



## Targets
Reference: [#109](https://github.com/gleam-lang/gleam/issues/109)

### Builtin
 - Erlang (BEAM)
 - Javascript (NodeJS/Bowser/Anywhere else JS runs)

### Other
#### Wasm
 - `Gleam->Erlang->Wasm`
    - [Firefly](https://github.com/GetFirefly/firefly)
    - [AtomVM](https://github.com/atomvm/AtomVM#readme)
 - `Gleam->Javascript->Wasm`
   - [Javy](https://github.com/bytecodealliance/javy)
   - [JCO](https://github.com/bytecodealliance/jco) ([ComponentizeJS](https://github.com/bytecodealliance/ComponentizeJS))
 - `Gleam->Wasm`
   - WIP - The person working on this is doing it as part of a school project, so not public at the moment.

<!-- TODO: Do some more research into the targets below -->
#### IoT / Microcontrollers / Embeded Devices
 - [AtomVM](https://github.com/atomvm/AtomVM#readme)
 - [Nerves](https://nerves-project.org/)

#### Desktop
 - [AtomVM](https://github.com/atomvm/AtomVM#readme)
 - [Tauri](https://tauri.app/) ([blog post](https://www.wezm.net/v2/posts/2024/gleam-tauri/))

#### Andriod
 - Use a JS engine to run Gleam compiled to JS (i.e. [Tauri](https://tauri.app/), [AndriodX JavascriptEngine](https://developer.android.com/develop/ui/views/layout/webapps/jsengine), [Zipline](https://github.com/cashapp/zipline), etc.)
 - Use Erlang/OTP compiled for Android ([Erlang OTP compiling guide](https://github.com/erlang/otp/blob/OTP-27.0/HOWTO/INSTALL-ANDROID.md), [demo](https://github.com/JeromeDeBretagne/erlanglauncher))


## Does Gleam Have A Garbage Collector?
Gleam does not have it own runtime. It compiles to Erlang and Javascript which both have garbage collectors. Don't let having a garbage collector fool you into thinking it's slow though, Erlang (BEAM) powers giants like Discord and WhatsApp.



## Division By Zero 
Gleam doesn't throw errors unless explicitly told to do so. So it just doesn't throw an error. There is also [this](https://www.hillelwayne.com/post/divide-by-zero/) article that goes into more details. Also see the [Int](https://hexdocs.pm/gleam_stdlib/gleam/int.html) and [float](https://hexdocs.pm/gleam_stdlib/gleam/float.html) docs.



## Views On Crashing / Throwing Errors
See the `Division By Zero` section.



## Gleam Written In Gleam (Bootstraping The Gleam Compiler)
No, this is probably never gonning happen. It's easier to bootstrap a language when it's still young and small, not when it hits `1.0`. And as Louis said:

> "It would be many years of rework to get back to the same point and we’d have worse performance. Big waste of time as even if it went perfectly we’d just be back to where we were before minus whatever we would have gained from using those years on the existing compiler."



## Name For People Who Use Gleam
`Gleamlins`. There's also Glemlins, Gleamers, and a few other ones, but we prefer Gleamlins.



## Can Gleam Interop With...? (FFI)
Gleam has builtin FFI support for Javascript and Erlang. Any other languages have to be done through Javascript's or Erlang's FFI for your language. For example WASM for JS and NIFs for Erlang. There's also this [blog post](https://www.jonashietala.se/blog/2024/01/11/exploring_the_gleam_ffi/) about Gleam's FFI.



## Operator Overloading/Defining New Operators
No. Gleam is designed to be simple and this would defeat that. If you realy want this than look into some sort of templating.
<!-- TODO: Make a library for this. Use cases: JSX, operator overloading, math libraries, etc. I want to make this but idk how soon I'll get around to it. -->



## Constants/Variables Aren't Immutable?
Actually, they are. You're reallying just seeing shadowing in effect. The original value isn't mutated, it's just hidden by another defintion by the same name farther down. Shadowing only affects local scope and doesn't mutate the orignal value.



## Does Gleam Have `X` Datastructure?
This [blog post](https://mckayla.blog/posts/all-you-need-is-data-and-functions.html) explores why Gleam only has data and functions, and not a multitude of data-structures.


## InteliJ Support
Unfortunately InteliJ doesn't support LSP<sup>`§`</sup>, the standard protocol for IDE tooling. Due to their unwillingness to implement the LSP protocol, IDE tooling maintainers either need a complex LSP to InteliJ translation layer or rewrite all their tooling for one single editor. Both options are terrible, so it's unlikely that Gleam will have offical support for InteliJ. There are however a few (old) community projects for InteliJ support.

`§` - Basic support is in paid version but very basic and not in free version



## No Loops?
Gleam is a functional programing language which don't have loops. In functional languages you just use recurrsion. Infinite recursion is also very efficent in functional languages. Details as to why can be found [here](https://beautifulracket.com/explainer/recursion.html).
