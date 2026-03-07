# mgit

A minimal Git implementation written in Erlang as an escript.

This project is a learning exercise to understand Git internals by building a simplified version from scratch.

## Reference

This implementation is based on the following Zenn book:

https://zenn.dev/ryu_9845343/books/fc32a59e1a3807

## Features

- `init` - Initialize a new mgit repository (creates `.mgit` directory with `objects`, `refs/heads`, `HEAD`, and `index`)
- `add <filename>` - Add a file to the staging area (computes SHA1 hash, stores compressed object, updates index)

## Usage

```sh
# Make the script executable
chmod +x mgit

# Initialize a repository
./mgit init

# Add a file to the staging area
./mgit add hello.txt
```

## Repository Structure

Running `mgit init` creates the following structure:

```text
.mgit/
  HEAD          # Points to the current branch (refs/heads/master)
  index         # Staging area (stores "path sha1" entries per line)
  objects/      # Object store (zlib-compressed files keyed by SHA1 hash)
  refs/
    heads/
      master    # Master branch reference
```

## Requirements

- Erlang/OTP (with escript support)
