[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/banner2-direct.svg)](https://vshymanskyy.github.io/StandWithUkraine)

# Awesome WebAssembly Tools [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A collection of useful, language-agnostic WebAssembly development tools.

[<img height="100" src="/images/code-explorer.png">](https://raw.githubusercontent.com/vshymanskyy/awesome-wasm-tools/main/images/code-explorer.png)
[<img height="100" src="/images/wasm-opt-callgraph.svg">](https://raw.githubusercontent.com/vshymanskyy/awesome-wasm-tools/main/images/wasm-opt-callgraph.svg)
[<img height="100" src="/images/wasm3-strace.png">](https://raw.githubusercontent.com/vshymanskyy/awesome-wasm-tools/main/images/wasm3-strace.png)
[<img height="100" src="/images/chrome-dev-tools.png">](https://raw.githubusercontent.com/vshymanskyy/awesome-wasm-tools/main/images/chrome-dev-tools.png)

👉 Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md). 😎


## Inspecting

- **WebAssembly Code Explorer** | [online tool](https://wasdk.github.io/wasmcodeexplorer/)  
  A simple binary explorer with neat binary code highlighting.

- **Weave** | [online tool](https://evmar.github.io/weave)  
  Another simple binary explorer.

- **wasm-opt** | part of [`Binaryen`](https://github.com/WebAssembly/binaryen)  
  - Color output of s-expression format:  
    `wasm-opt --print test.wasm`
  - Plot the callgraph using `Graphviz`:  
    `wasm-opt --print-call-graph test.wasm | dot -Tpng -o callgraph.png`
  - Dump DWARF debug info sections:  
    `wasm-opt --dwarfdump test.wasm`
  - Print function metrics:  
    `wasm-opt --func-metrics test.wasm`

- **wasm-decompile** | part of [`WABT`](https://github.com/WebAssembly/wabt), [article](https://v8.dev/blog/wasm-decompile)  
  `wasm-decompile` decompiles a wasm binary into readable code. It generates output that tries to look like a "very average programming language" while still staying close to the wasm it represents.

- **wasmdec** | [repo](https://github.com/wwwg/wasmdec), [online tool](https://wwwg.github.io/web-wasmdec/)  
  Converts WebAssembly binaries to C. Similar to `wasm2c`.

- **wasp** | [repo](https://github.com/WebAssembly/wasp)  
  Generate callgraphs, CFG and DFG graphs for wasm functions.

- **wasm-objdump** | part of [`WABT`](https://github.com/WebAssembly/wabt)  
  Print low-level details about a `.wasm` binary and each of its sections.

- **wasm-nm** | [repo](https://github.com/fitzgen/wasm-nm)  
  List the imported, exported, and private function symbols defined within a `.wasm` binary.

- **Modsurfer** | [home](https://www.dylibso.com/), [repo](https://github.com/dylibso/modsurfer)  
  Diagnostics and auditing tool for searching, browsing, validating, and investigating WebAssembly modules and components.


## Static analysis

- **Twiggy** | [repo](https://github.com/rustwasm/twiggy)  
  Code size profiler, analyzes a binary's call graph.

- **Manticore** | [repo](https://github.com/trailofbits/manticore), [article](https://blog.trailofbits.com/2020/01/31/symbolically-executing-webassembly-in-manticore/)  
  Symbolic execution of WebAssembly binaries.

- **Owi** | [docs](https://ocamlpro.github.io/owi/), [repo](https://github.com/OCamlPro/owi)  
  Framework for WebAssembly analysis and manipulation, with a focus on practical symbolic execution.
  
- **Octopus** | [repo](https://github.com/pventuzelo/octopus)  
  Security analysis framework for WebAssembly modules and Smart Contracts.
  
- **Wassail** | [repo](https://github.com/acieroid/wassail)  
  A toolkit to perform both lightweight and heavyweight static analysis of WebAssembly modules.

- **wasm-opcodecnt** | part of [`WABT`](https://github.com/WebAssembly/wabt)  
  Count wasm opcode usage statistics.


## Manipulating (optimization, transformation, instrumentation)

- **wasm-opt** | part of [`Binaryen`](https://github.com/WebAssembly/binaryen)  
  - Transform binary for asynchronous execution (read more in [this article](https://kripken.github.io/blog/wasm/2019/07/16/asyncify.html)):  
    `wasm-opt test.wasm --asyncify -O3 -o asyncified.wasm`
  - Instrument binary for dynamic execution tracing:  
    `wasm-opt test.wasm --instrument-memory --instrument-locals --log-execution -o instrumetred.wasm`

- **wizer** | [repo](https://github.com/bytecodealliance/wizer)  
  Don't wait for your Wasm module to initialize itself, pre-initialize it! Wizer instantiates your WebAssembly module, executes its initialization function, and then snapshots the initialized state out into a new WebAssembly module.

- **wasm2c** | part of [`WABT`](https://github.com/WebAssembly/wabt/blob/main/wasm2c/README.md), 
[article 1](https://kripken.github.io/blog/wasm/2020/07/27/wasmboxc.html), 
[article 2](https://petersalomonsen.com/articles/wasm2c/wasm2c.html)  
  Takes a WebAssembly module and produces an equivalent (and runnable) C source and header.
  
- **wasm-snip** | [repo](https://github.com/rustwasm/wasm-snip)  
  Replaces a WebAssembly function's body with an `unreachable`.

- **wasmonkey** | [repo](https://github.com/jedisct1/wasmonkey)  
  Magically turns exported WASM functions into imported functions.

- **wasm-meter** | [npm](https://www.npmjs.org/package/wasm-metering), [repo](https://github.com/ewasm/wasm-metering)  
  Injects metering into webassembly binaries. This counts computation time for a given program in units of `gas` (and allows limiting it).

- **CROW** | [repo](https://github.com/KTH/slumps/tree/master/crow)  
  The Wasm superdiversifier. It takes C source code or LLVM bitcode as input and generates several functionally equivalent, but diverse Wasm binaries.  

- **watr** | [repo](https://github.com/dy/watr), [npm](https://www.npmjs.com/package/watr), [demo](https://dy.github.io/watr/)  
  Light and fast WAT compiler for compiling, parsing, printing, formatting, optimizing, and polyfilling WebAssembly text.


## Component Model and WIT

- **jco** | [docs](https://bytecodealliance.github.io/jco/), [repo](https://github.com/bytecodealliance/jco)  
  JavaScript-native toolchain for working with WebAssembly Components, including transpiling components to ES modules and creating components from JavaScript.

- **ComponentizeJS** | [repo](https://github.com/bytecodealliance/ComponentizeJS)  
  Tool for turning JavaScript modules into WebAssembly components.

- **wit-bindgen** | [repo](https://github.com/bytecodealliance/wit-bindgen)  
  Guest language bindings generator for WIT and the WebAssembly Component Model.

- **wac** | [repo](https://github.com/bytecodealliance/wac), [docs](https://component-model.bytecodealliance.org/composing-and-distributing/composing.html)  
  WebAssembly Compositions tool for composing components together from the command line or from `.wac` composition files.

- **cargo-component** | [repo](https://github.com/bytecodealliance/cargo-component), [crate](https://crates.io/crates/cargo-component)  
  Cargo subcommand for building Rust WebAssembly components from WIT worlds.

- **wkg, wasm-pkg-tools** | [repo](https://github.com/bytecodealliance/wasm-pkg-tools), [crate](https://crates.io/crates/wkg)  
  Tools for fetching and publishing WebAssembly components and WIT packages to OCI or Warg registries.

- **WASI-Virt** | [repo](https://github.com/bytecodealliance/WASI-Virt)  
  Virtualization component generator for WASI Preview 2 APIs, useful for encapsulating or restricting component access to host capabilities.


## Dynamic analysis (tracing, profiling)

- **wasm3-strace** | [wapm](https://wapm.io/package/vshymanskyy/wasm3), [repo](https://github.com/wasm3/wasm3)  
  Structured, seamless tracing of arbitrary WebAssembly/WASI execution.

- **Wasabi** | [home](http://wasabi.software-lab.org/), [repo](https://github.com/danleh/wasabi)  
  "WebAssembly analysis using binary instrumentation", a dynamic analysis framework.

- **wasmsign2** | [repo](https://github.com/wasm-signatures/wasmsign2)  
  A tool to add and verify digital signatures to/from WASM binaries.

- **swam** | [repo](https://github.com/satabin/swam/)  
  A WASM interpreter with advanced tracing capabilities.

## Editing

- **wasm-language-tools** | [home](https://wasm-language-tools.netlify.app/), [repo](https://github.com/g-plane/wasm-language-tools)  
  Language server and formatter for WebAssembly Text Format, with completion, diagnostics, navigation, inlay hints, and call hierarchy.

- **Hexana** | [docs](https://jetbrains.github.io/hexana/), [repo](https://github.com/JetBrains/hexana)  
  WebAssembly and binary analysis toolkit for JetBrains IDEs and VS Code, including structured `.wasm` inspection, WAT and WIT support, and run/debug integrations.

- **vscode-wit** | [repo](https://github.com/bytecodealliance/vscode-wit)  
  Visual Studio Code extension for WIT, with syntax highlighting, validation, formatting, bindings generation, and component inspection.

## Source-level debugging

- **Chrome DevTools** | [article](https://developers.google.com/web/updates/2020/12/webassembly)

- **LLDB** | [article](https://hacks.mozilla.org/2019/09/debugging-webassembly-outside-of-the-browser/)

- **wasminspect** | [repo](https://github.com/kateinoigakukun/wasminspect)  
  An interactive and self-contained debugger for WebAssembly/WASI.


## Tool development

- **Tool Conventions** | [docs](https://github.com/WebAssembly/tool-conventions)  
  Documents describing conventions useful for coordinating interoperability between wasm-related tools.

- **Binaryen** | [repo](https://github.com/WebAssembly/binaryen)  
  WebAssembly compiler and toolchain infrastructure with tools for parsing, emitting, optimizing, interpreting, reducing, merging, and compiling WebAssembly.

- **WABT** | [repo](https://github.com/WebAssembly/wabt)  
  The WebAssembly Binary Toolkit, a suite of command-line tools for converting, inspecting, validating, and manipulating WebAssembly binaries and text.

- **Javy** | [repo](https://github.com/bytecodealliance/javy)  
  JavaScript-to-WebAssembly toolchain based on QuickJS, producing compact WASI modules.

- **wasm2json, json2wasm** | [npm](https://www.npmjs.com/package/wasm-json-toolkit), [repo](https://github.com/ewasm/wasm-json-toolkit)  
  A small toolkit for converting wasm binaries into json and back. Incredibly helpful for experimenting and creating your own transformations.

- **walrus** | [repo](https://github.com/rustwasm/walrus)  
  Rust library for performing WebAssembly transformations in a robust and ergonomic fashion.

- **waffle** | [repo](https://github.com/bytecodealliance/waffle), [crate](https://crates.io/crates/waffle)  
  Rust SSA IR framework for WebAssembly analysis and Wasm-to-Wasm transforms.

- **wasp** | [repo](https://github.com/WebAssembly/wasp)  
  C++ library designed to make it easy to work with WebAssembly modules.

- **Binaryen.js** | [repo](https://github.com/AssemblyScript/binaryen.js)  
  A port of Binaryen to the Web, allowing you to generate WebAssembly using JavaScript.

- **wasm-tools** | [repo](https://github.com/bytecodealliance/wasm-tools)  
  Rust tooling for low-level manipulation of WebAssembly modules.  
    `wasm-smith` test case generator is of particular interest.  
    `wasm-shrink` shrinks a Wasm file while preserving an interesting property (such as triggering a bug).

- **wasm-debug** | [repo](https://github.com/wasmerio/wasm-debug), [crate](https://crates.io/crates/wasm-debug)  
  A runtime-independent Rust library that provides functionality to read, transform, and write DWARF section.

- **witx-codegen** | [repo](https://github.com/jedisct1/witx-codegen)  
  A code generator to access WebAssembly standard APIs from different programming languages. Can also generate documentation.

- **Articles**
  - [Fuzzers & Reducers as Productivity Tools](https://kripken.github.io/blog/binaryen/2019/06/11/fuzz-reduce-productivity.html)


## Application frameworks and deployment

- **Extism** | [home](https://extism.org/), [repo](https://github.com/extism/extism)  
  Cross-language framework for building WebAssembly-based plugin systems with host SDKs and guest PDKs.

- **Spin** | [home](https://spinframework.dev/), [repo](https://github.com/spinframework/spin)  
  Framework and CLI for building, running, and distributing serverless WebAssembly applications.

- **wasmCloud, wash** | [docs](https://wasmcloud.com/docs/wash/), [repo](https://github.com/wasmCloud/wasmCloud)  
  Cloud-native platform and CLI for developing, building, publishing, and running WebAssembly components.

- **SpinKube** | [home](https://www.spinkube.dev/), [repos](https://github.com/spinframework)  
  Kubernetes-native stack for deploying and operating Spin-based WebAssembly workloads.

- **runwasi** | [docs](https://runwasi.dev/), [repo](https://github.com/containerd/runwasi)  
  Containerd shim infrastructure for running WebAssembly workloads through containerd and Kubernetes.


## Other

- **WebAssembly Opcode Table** | [docs](https://wasm-chart.pengowray.com/)

- **WebAssembly Feature Status** | [docs](https://webassembly.org/features/)  
  Matrix tracking WebAssembly feature support across popular browsers, standalone runtimes, and tools.
