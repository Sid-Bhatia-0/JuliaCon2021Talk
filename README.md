# JuliaCon2021Talk

Supplementary material and details for my JuliaCon 2021 lightning talk.

### Getting Started

You can use the `Project.toml` and `Manifest.toml` files in this repository to reproduce the project environment and following along with the talk.

Clone this project, go inside the project directory, and start the julia REPL:

```julia
JuliaCon2021Talk $ julia
               _
   _       _ _(_)_     |  Documentation: https://docs.julialang.org
  (_)     | (_) (_)    |
   _ _   _| |_  __ _   |  Type "?" for help, "]?" for Pkg help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 1.6.1 (2021-04-23)
 _/ |\__'_|_|_|\__'_|  |  Official https://julialang.org/ release
|__/                   |

julia> VERSION
v"1.6.1"

julia> import Pkg

julia> Pkg.activate(".");

julia> Pkg.instantiate(); # this might take a while

julia>
```

### Code for Interactive Playing & Recording

To see the code for interactive playing and recording, you can check out the following file from the [`GridWorlds`](https://github.com/JuliaReinforcementLearning/GridWorlds.jl) package:

[https://github.com/JuliaReinforcementLearning/GridWorlds.jl/blob/master/src/play.jl](https://github.com/JuliaReinforcementLearning/GridWorlds.jl/blob/master/src/play.jl)

This is a more robust version of the code was used for the demo in the talk. Also, this file is mostly self-contained, so it should be relatively easy to understand what is going here without having to understand other parts of the GridWorlds package.

I recommend checking out the latest version. But nevertheless, here is a link to the commit from the `GridWorlds` package that was used in this talk:

[https://github.com/JuliaReinforcementLearning/GridWorlds.jl/tree/9a0b1bb9871bffd7f135583b3cda0d583cf6c5b6](https://github.com/JuliaReinforcementLearning/GridWorlds.jl/tree/9a0b1bb9871bffd7f135583b3cda0d583cf6c5b6)

### Ray-Caster Example

The ray casting examlpe is from the `RayCastWorlds` package. It uses another package called `RayCaster` for the core ray-casting algorithm:

[https://github.com/Sid-Bhatia-0/RayCaster.jl](https://github.com/Sid-Bhatia-0/RayCaster.jl)

As of this writing, `RayCastWorlds` is not a registered package. Here is a link to the commit from the `RayCastWorlds` package that was used in this talk:

[https://github.com/Sid-Bhatia-0/RayCastWorlds.jl/tree/6b8bffa2e4bc129a762cff8551491e39eb0ee87c](https://github.com/Sid-Bhatia-0/RayCastWorlds.jl/tree/6b8bffa2e4bc129a762cff8551491e39eb0ee87c)

To visualize the ray caster, you may need to set the terminal in full screen mode and decrease the font-size of your terminal to correctly fit the visualation on the screen.

After instantiating the project environment for this talk, do the following:

```julia
julia> import RayCastWorlds as RCW

julia> game = RCW.SingleRoomGameModule.SingleRoomGame(num_directions = 256);

julia> RCW.SingleRoomGameModule.play!(game)
```

Here are the key-bindings:
1. `q`: quit
1. `w`: move forward
1. `s`: move backward
1. `a`: turn left
1. `d`: turn right
1. `v`: switch between camera view and top view

### Other Resources

The following files from the REPL package in Julia have been crucial in helping me understand and implement REPL-based interactivity:

1. [https://github.com/JuliaLang/julia/blob/master/stdlib/REPL/src/TerminalMenus/AbstractMenu.jl](https://github.com/JuliaLang/julia/blob/master/stdlib/REPL/src/TerminalMenus/AbstractMenu.jl)
1. [https://github.com/JuliaLang/julia/blob/master/stdlib/REPL/src/Terminals.jl](https://github.com/JuliaLang/julia/blob/master/stdlib/REPL/src/Terminals.jl)

If you want to learn more about how terminal emulators work, I highly recommend checking out this talk from JuliaCon 2020 by Dheepak Krishnamurthy:

[https://www.youtube.com/watch?v=-TASx67pphw](https://www.youtube.com/watch?v=-TASx67pphw)
