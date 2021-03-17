# Awesome WebAssembly Tools [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A collection of WebAssembly development tools.

Please read the [contribution guidelines](CONTRIBUTING.md) if you want to contribute.


## Inspecting

- **WebAssembly Code Explorer** | [online tool](https://wasdk.github.io/wasmcodeexplorer/)  

- **wasm-opt --print** | part of [`Binaryen`](https://github.com/WebAssembly/binaryen)  

- **wasm-objdump** | part of [`WABT`](https://github.com/WebAssembly/wabt)  
  Print low-level details about a `.wasm` binary and each of its sections.

- **wasm-nm** | [repo](https://github.com/fitzgen/wasm-nm)  
  List the imported, exported, and private function symbols defined within a `.wasm` binary.


## Static analysis

- **Twiggy** | [repo](https://github.com/rustwasm/twiggy)  
  Code size profiler, analyzes a binary's call graph.

- **Manticore** | [repo](https://github.com/trailofbits/manticore), [article](https://blog.trailofbits.com/2020/01/31/symbolically-executing-webassembly-in-manticore/)  
  Symbolical execution of WebAssembly binaries.


## Manipulating (optimization, transformation, instrumentation)

- **wasm-opt** | part of [`Binaryen`](https://github.com/WebAssembly/binaryen)  

- **wizer** | [repo](https://github.com/bytecodealliance/wizer)  
  Don't wait for your Wasm module to initialize itself, pre-initialize it! Wizer instantiates your WebAssembly module, executes its initialization function, and then snapshots the initialized state out into a new WebAssembly module. 

- **wasm-snip** | [repo](https://github.com/rustwasm/wasm-snip)  
`wasm-snip` replaces a WebAssembly function's body with an `unreachable`.

- **wasm-meter** | [npm](https://www.npmjs.org/package/wasm-metering), [repo](https://github.com/ewasm/wasm-metering)  
Injects metering into webassembly binaries. The metering counts computation time for a given program in units of `gas`.

- **walrus** | [repo](https://github.com/rustwasm/walrus)  
A rust library for performing WebAssembly transformations.

- **wasm2json, json2wasm** | [npm](https://www.npmjs.com/package/wasm-json-toolkit), [repo](https://github.com/ewasm/wasm-json-toolkit)  
A small toolkit for converting wasm binaries into json and back. Very helpful for creating your own, custom transformations.


## Dynamic analysis, profiling

- **wasm3-trace** | [wapm](https://wapm.io/package/vshymanskyy/wasm3), [repo](https://github.com/wasm3/wasm3)  
  Structured, seamless tracing of arbitrary WebAssembly/WASI execution.

- **wasm-profiler** | [repo](https://github.com/dfinity/wasm-profiler)  
  Instruction counting profiler for Wasm

- **Wasabi** | [home](http://wasabi.software-lab.org/), [repo](https://github.com/danleh/wasabi)  
  "WebAssembly analysis using binary instrumentation", a dynamic analysis framework.


## Other

- **WebAssembly Opcode Table** | [online tool](https://pengowray.github.io/wasm-ops/)  

- **Webassembly.sh** | [online tool](https://webassembly.sh)  
