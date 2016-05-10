# Miri

An experimental compiler from [Rust] to [WebAssembly], based on rustc + Rust [MIR].

**This doesn't do anything useful yet.**

## Download Rust nightly

I currently recommend that you install [rustup] and then use it to
install the current rustc nightly version:

```sh
git clone https://github.com/brson/mir2wasm.git
cd mir2wasm
rustup override nightly
```

## Build && run

```sh
cargo build
```

```sh
cargo run -- --sysroot=`rustc --print sysroot` rust-examples/smallest-hello-world.rs
```

## Debugging

Log stuff:

```
RUST_LOG=mir2wasm cargo run -- --sysroot=`rustc --print sysroot` rust-examples/smallest-hello-world.rs
```

Dump the mir map:

```
rustc -Z unstable-options --unpretty=mir rust-examples/smallest-hello-world.rs
```

## rustc docs

https://manishearth.github.io/rust-internals-docs/rustc/index.html

## License

Licensed under either of
  * Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or
    http://www.apache.org/licenses/LICENSE-2.0)
  * MIT license ([LICENSE-MIT](LICENSE-MIT) or
    http://opensource.org/licenses/MIT) at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you shall be dual licensed as above, without any
additional terms or conditions.

[Rust]: https://www.rust-lang.org/
[WebAssembly]: https://webassembly.github.io/
[MIR]: https://github.com/rust-lang/rfcs/blob/master/text/1211-mir.md
[rustup]: https://www.rustup.rs
