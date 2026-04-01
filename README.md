# brainfuck-rave

Efficient Brainfuck interpreter written in [Rave](https://github.com/Ttimofeyka/Rave) programming language.

## Features

- **O(1) loop jumps** - Precomputed bracket matching for fast execution
- **Circular tape** - 30,000 cell tape with wraparound pointer
- **File and stdin support** - Load from `.bf` files or pipe code directly
- **Proper byte wrapping** - Cells wrap correctly at 0-255

## Building

Requires the Rave compiler.

```bash
rave main.rave -o bf -Ofast
```

## Usage

```bash
# Run from file
./bf examples/hello.bf

# Pipe code directly
echo "++++++++++[>+++++++>++++++++++>+++>+<<<<-]>++.>+.+++++++..+++.>++.<<+++++++++++++++.>.+++.------.--------.>+.>." | ./bf

# Interactive input (programs using ',' command)
./bf examples/cat.bf
```

## Brainfuck Commands

| Command | Description |
|---------|-------------|
| `+` | Increment current cell |
| `-` | Decrement current cell |
| `>` | Move pointer right |
| `<` | Move pointer left |
| `.` | Output cell as ASCII |
| `,` | Read one byte into cell |
| `[` | Jump to matching `]` if cell is zero |
| `]` | Jump to matching `[` if cell is nonzero |

## License

MIT
