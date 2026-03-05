# mgit

A minimal Git implementation written in Erlang as an escript.

This project is a learning exercise to understand Git internals by building a simplified version from scratch.

## Reference

This implementation is based on the following Zenn book:

https://zenn.dev/ryu_9845343/books/fc32a59e1a3807

## Features

- `init` - Initialize a new mgit repository (creates `.mini_git` directory with `objects`, `refs/heads`, `HEAD`, and `index`)

## Usage

```sh
# Make the script executable
chmod +x mgit

# Initialize a repository
./mgit init
```

## Repository Structure

Running `mgit init` creates the following structure:

```
.mini_git/
  HEAD          # Points to the current branch (refs/heads/master)
  index         # Staging area
  objects/      # Object store
  refs/
    heads/
      master    # Master branch reference
```

## Requirements

- Erlang/OTP (with escript support)
