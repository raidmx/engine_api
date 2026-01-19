# Engine API

A Rust API for interfacing with Minecraft: Bedrock Edition data structures.

## Features

### NBT Support

Provides a complete NBT (Named Binary Tag) implementation:

- **Tag Types**: All standard NBT tags (Byte, Short, Int, Long, Float, Double, String, ByteArray, IntArray, LongArray, List, Compound)
- **Compound Tags**: Key-value storage with type-safe access
- **List Tags**: Homogeneous collections of NBT values
- **Type Conversions**: Seamless conversion between Rust types and NBT

```rust
use engine_api::nbt::{NBT, Compound, List, Tag};

// Create a compound tag
let mut compound = Compound::new();
compound.insert("name", NBT::String("Player".to_string()));
compound.insert("health", NBT::Float(20.0));

// Access values
let name = compound.get("name").unwrap().as_string();
```

## Installation

Add to your `Cargo.toml`:

```toml
[dependencies]
engine_api = { git = "https://github.com/raidmx/engine_api" }
```

## Building

```bash
cargo build --release
```

## Testing

```bash
cargo test
```

## License

MIT
