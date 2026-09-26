# Zifer for VS Code

Syntax highlighting and snippets for the [Zifer](https://github.com/zifer-lang/zifer) backend language.

## Features

- Syntax highlighting for `.zf` files
- Snippets: `fn`, `server`, `route`, `model`, `try`, `async`
- Bracket matching & auto-closing pairs

## Requirements

None — this is a grammar-only extension. Install the Zifer CLI separately:

```bash
curl -fsSL https://raw.githubusercontent.com/zifer-lang/zifer/main/install.sh | bash
```

## Building locally

```bash
npm install
npx vsce package
code --install-extension zifer-lang-0.1.0.vsix
```
