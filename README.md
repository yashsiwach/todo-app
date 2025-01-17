# todo-app

A simple TODO app in Haskell that provides a persistent way to manage the TODO list, by making HTTP requests to Postgrest (postgrest is a web server that converts your PostgreSQL database into a RESTful API).


**This app serves as a hello-world to ultimately demonstrate how a Haskell project can benefit from the use of Nix (to be precise, [haskell-flake](https://haskell.flake.page) and [flake-parts](https://flake.parts)).**

## Prerequisite

- Install Nix<sup>[(*)](https://determinate.systems/posts/determinate-nix-installer)</sup>, enable Flakes (avoid using global installations)
- Stop any global postgres server on port 5432.
- Run `nix run .#postgres` to start a postgres server with data dir in `./data/db`.
- Run `nix run .#createdb` to create DB user, load the dump and create the DB configuration for PostgREST.
- Run `nix run .#postgrest` to start PostgREST web server.

## Getting Started

- Run `nix build` that will symlink the executable at `./result/bin/todo-app`.
- `cd result/bin`.
- Run `./todo-app --help` to see the list of actions you can perform.

