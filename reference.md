# Gleam Reference


<!-- TODO: Dynamic table of contents here -->


## Targets
Refrence: [#109](https://github.com/gleam-lang/gleam/issues/109)

### Builtin
 - Erlang (BEAM)
 - Javascript (NodeJS/Bowser/Anywhere else JS runs)

### Other
#### WASM
 - `Gleam->Erlang->WASM`
    - [Firefly](https://github.com/GetFirefly/firefly)
    - [AtomVM](https://www.atomvm.net/)
 - `Gleam->Javascript->WASM`
   - [Javy](https://github.com/bytecodealliance/javy)
   - [JCO](https://github.com/bytecodealliance/jco) ([ComponentizeJS](https://github.com/bytecodealliance/ComponentizeJS))

<!-- TODO: Do some more research into the targets below -->
#### IoT / Microcontrollers / Embeded Devices
 - [AtomVM](https://www.atomvm.net/)

#### Desktop
 - [AtomVM](https://www.atomvm.net/)
 - [Tauri](https://tauri.app/) ([blog post](https://www.wezm.net/v2/posts/2024/gleam-tauri/))

#### Andriod
 - JS in WebView (e.g. [Tauri](https://tauri.app/))



## Division By Zero 
Gleam doesn't throw errors unless explicitly told to do so. So it just doesn't throw an error. There is also [this](https://www.hillelwayne.com/post/divide-by-zero/) article that goes into more details. Also see the [Int](https://hexdocs.pm/gleam_stdlib/gleam/int.html) and [float](https://hexdocs.pm/gleam_stdlib/gleam/float.html) docs.



## Crashing / Throwing Errors
See the `Division By Zero` section.



## Gleam Written In Gleam (Bootstraping The Gleam Compiler)
No, this is probably never gonning happen. It's easier to bootstrap a language when it's still young and small, not when it hits `1.0`. As Louis said,  ... <!-- TODO: Add a quote from Discord explaining talking about this -->



## Name For People Who Use Gleam
Gleamlins, Glemlins, Gleamers, idk, we havn't settled on one yet. Gleamlins is a popular one right now.



## Can Gleam Interop With...?
Gleam has builtin FFI support for Javascript and Erlang. Any other languages have to be done through Javascript's or Erlang's FFI for your language. For example WASM for JS and NIFs for Erlang.



## Operator Overloading/Defining New Operators
No. Gleam is designed to be simple and this would defeat that. If you realy want this than look into some sort of templating.
<!-- TODO: Make a library for this. Use cases: JSX, operator overloading, math libraries, etc. I want to make this but idk how soon I'll get around to it. -->



## Constants Aren't Immutable?
They actually are, you're probably seeing shadowing in effect. Shadowing only affects local scope and doesn't mutate the orignal value. However, if it somehow turns out not to be shadowing, then please submit a bug report! 🥺🙏



## InteliJ Support
Unfortunately InteliJ doesn't support LSP<sup>`§`</sup>, the standard protocol for IDE tooling. Due to their unwillingness to implement the LSP protocol, IDE tooling maintainers either need a complex LSP to InteliJ translation layer or rewrite all their tooling for one single editor. Both options are terrible, so it's unlikely that Gleam will have offical support for InteliJ. There are however a few (old) community projects for InteliJ support.

`§` - Basic support is in paid version but very basic and not in free version
