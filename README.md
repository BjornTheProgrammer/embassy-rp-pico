# embassy-rp-pico
This is a starter example for the Raspberry Pi Pico for embassy-rs in Rust.

## Setup
1. Install [rustup](https://www.rust-lang.org/).
2. Install the `thumbv6m-none-eabi` toolchain via `rustup target add thumbv6m-none-eabi`.
3. Install `elf2uf2-rs` with `cargo install elf2uf2-rs`.

## Running
1. Plug in your Raspberry Pi Pico to your computer while holding down the button.
2. Run `cargo run`

## Project Structure
The project structure is pretty simple, and is as follows.
```
embassy-rp-pico
├── .cargo
├   └── config.toml
├── Cargo.lock
├── Cargo.toml
├── build.rs
├── memory.x
└── src
    └── main.rs
```
The `memory.x` file specifies how the boot, flash, and ram are partitioned within the program.

The `build.rs` file imports the `memory.x` file into the executable.

The `.cargo/config.toml` file tells cargo to compile using the `thumbv6m-none-eabi` toolchain, and run `elf2uf2-rs` upon the program compiling.

The `Cargo.toml` contains all of the dependencies used, and the `Cargo.lock` is the output of that process.

Finally the `src/main.rs` contains the code to be run on the Raspberry Pi Pico.
