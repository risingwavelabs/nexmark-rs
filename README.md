# Nexmark-rs

[![Crate](https://img.shields.io/crates/v/nexmark.svg)](https://crates.io/crates/nexmark)
[![Docs](https://docs.rs/nexmark/badge.svg)](https://docs.rs/nexmark)
[![CI](https://github.com/risingwavelabs/nexmark-rs/workflows/CI/badge.svg?branch=main)](https://github.com/risingwavelabs/nexmark-rs/actions)

The [Nexmark benchmark](https://github.com/nexmark/nexmark) data generator in Rust.

## Installation

```sh
cargo install nexmark --features bin
```

## Usage

Generate nexmark events. Print one per line in JSON format:

```sh
nexmark
```

Only generate events for a specific type:

```sh
nexmark -t person
```

By default it generates events at a certain rate based on the timestamp. You can make it generate all at once by adding `--no-wait`:

```sh
nexmark -n 10 --no-wait
```

See more usages:

```sh
nexmark -h
```

## Using as Library

Add nexmark to your Cargo.toml:

```sh
cargo add nexmark
```

Generate events from the generator:

```rust
use nexmark::EventGenerator;

for event in EventGenerator::default().take(10) {
    println!("{event:?}");
}
```

## License

Apache License 2.0. Please refer to [LICENSE](LICENSE) for more information.
