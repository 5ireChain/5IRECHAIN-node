# 5IRECHAIN: A sustainability-driven score based blockchain with a benefit-focused paradigm

5IRECHAIN is a sustainability EVM Compatible chain built on the next-generation blockchain framework substrate, the first of its kind with a cutting edge efficient secure scalable and speedy consensus "Fire score" that incentivized all the network participant to show activities on-chain that are compatible with a for-benefit paradigm driven by a charity perspective and appliance with the 17 United Nations Sustainable Development Goals.


A fresh FRAME-based [Substrate] node, ready for exploring Beta version :rocket:

## Getting Started

Follow the steps below to get started with the Node Template, :hammer_and_wrench:

### Using Nix

Install [nix](https://nixos.org/) and optionally [direnv](https://github.com/direnv/direnv) and [lorri](https://github.com/target/lorri) for a fully plug
and play experience for setting up the development environment. To get all the correct dependencies activate direnv `direnv allow` and lorri `lorri shell`.

### Rust Setup

First, complete the [basic Rust setup instructions](./docs/rust-setup.md).

### Run

Use Rust's native `cargo` command to build and launch the template node:

```sh
cargo run --release -- --dev --tmp
```

### Build

The `cargo run` command will perform an initial build. Use the following command to build the node
without launching it:

```sh
cargo build --release
```


## Run

The provided `cargo run` command will launch a temporary node and its state will be discarded after
you terminate the process. After the project has been built, there are other ways to launch the
node.

### Single-Node Development Chain

This command will start the single-node development chain with persistent state:

```bash
./target/release/node-template --dev
```

Purge the development chain's state:

```bash
./target/release/node-template purge-chain --dev
```

Start the development chain with detailed logging:

```bash
RUST_LOG=debug RUST_BACKTRACE=1 ./target/release/node-template -lruntime=debug --dev
```


First, install [Docker](https://docs.docker.com/get-docker/) and
[Docker Compose](https://docs.docker.com/compose/install/).

Then run the following command to start a single node development chain.

```bash
./scripts/docker_run.sh
```

This command will firstly compile your code, and then start a local development network. You can
also replace the default command (`cargo build --release && ./target/release/node-template --dev --ws-external`)
by appending your own. A few useful ones are as follow.

```bash
# Run Substrate node without re-compiling
./scripts/docker_run.sh ./target/release/node-template --dev --ws-external

# Purge the local dev chain
./scripts/docker_run.sh ./target/release/node-template purge-chain --dev

# Check whether the code is compilable
./scripts/docker_run.sh cargo check
```
