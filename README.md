# Emsnek

Emsnek is a utility for generating emscripten-forge recipes by utilizing conda-forge recipes.

## Project Motivation
Building science based projects on different platforms is difficult. There are complex webs of libraries from various languages. For example [pystan](https://github.com/stan-dev/pystan) no longer supports Windows because of these sorts of build difficulties. 

### Targeting web assembly
Web assembly (wasm) is a good cross platform target for a [universal binary](https://wasmer.io/posts/wasm-as-universal-binary-format-part-1-native-executables). Even if binaries were available for every system, the cross-platform graphical user interface of choice is the browser. Taken together there is a trend towards [progressive web applications](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/What_is_a_progressive_web_app) which can utilize both wasm and browser based front-ends. 

### Emscripten Forge
[Emscripten-forge](https://github.com/emscripten-forge/recipes) has been used successfully by [Jupyter Lite](https://blog.jupyter.org/mamba-meets-jupyterlite-88ef49ac4dc8) to build various projects such as scipy, numpy, and plotly directly in the browser for code notebooks. This is the exact sort of usage needed for science-based progressive web applications. Emscripten-forge needs many more recipe's to achieve comprehensive coverage of science based libraries.

## Usage

### Install babashka
You can [install babashka](https://github.com/babashka/babashka#installation).

If you are using nix then:
``` sh
nix-shell -p babashka
```

### Boify a package
``` sh
bin/boify <<conda-package-name>>
```

