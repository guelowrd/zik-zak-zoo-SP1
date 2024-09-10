# ZiK-ZaK-Zoo: A Provable Tic-Tac-Toe Game

This project implements a Tic-Tac-Toe game called ZiK-ZaK-Zoo using the [SP1](https://github.com/succinctlabs/sp1) framework. It demonstrates how to create a provable game where a player can generate a proof of their win against a computer opponent.

## Game Description

ZiK-ZaK-Zoo is a Tic-Tac-Toe variant where:
- The human player uses 'Z' as their symbol
- The computer uses 'K' as its symbol
- The game board is represented by numbers 0-8

The game logic includes:
- A simple random number generator for the computer's moves ([LCR](https://en.wikipedia.org/wiki/Linear_congruential_generator) with [MMIX](https://en.wikipedia.org/wiki/MMIX) parameters)
- Board state management
- Win condition checking

## Project Structure

The project consists of several key components:

1. Game Logic Library (`lib/src/lib.rs`)
2. Main Game Script (`script/src/bin/main.rs`)
3. Provable Program (`program/src/main.rs`)

## How It Works

1. The player plays a game against the computer.
2. The game records the seed used for the random number generator and the player's moves.
3. After the game, if the player wins, they can generate a proof of their win.
4. This proof can be verified on-chain, confirming the player's victory without revealing the exact moves.

## Running the Project

There are three main ways to interact with this project:

### Execute the Program

This runs the game without generating a proof:

```sh
cd script
cargo run --release -- --execute
```

### Generate a Core Proof

This generates a proof of the game outcome:

```sh
cd script
cargo run --release -- --prove
```

## Technical Details

- The game logic is implemented in Rust and compiled to RISC-V architecture.
- The SP1 framework is used to generate zero-knowledge proofs of game outcomes.
- The project includes scripts for executing the game, generating proofs, and retrieving verification keys.

For those interested in the implementation details:
- The main game logic can be found in the `lib/src/lib.rs` file.
- The script that runs the game and generates proofs is in `script/src/bin/main.rs`.
- The provable program that verifies the game outcome is in `program/src/main.rs`.

This project serves as an example of how to create provable games using zero-knowledge proofs, which can be useful for on-chain gaming applications where fairness and verifiability are crucial -- although this part is not implemented in this repo.