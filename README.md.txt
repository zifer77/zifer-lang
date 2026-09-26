# Zifer

![build](https://img.shields.io/github/actions/workflow/status/zifer-lang/zifer/ci.yml?branch=main)
![version](https://img.shields.io/github/v/release/zifer-lang/zifer)
![license](https://img.shields.io/badge/license-MIT-blue)

**Zifer** is a backend programming language designed to be installed and used like Node.js, PHP, or Go — but compiled ahead-of-time via LLVM for native performance.

- File extension: `.zf`
- Focus: APIs, servers, databases
- Goal: faster than Node.js, competitive with Go/Rust
- Compiler: written in Rust, native binaries via LLVM (interpreter fallback while codegen matures)

## Install

**Linux / macOS**
```bash
curl -fsSL https://raw.githubusercontent.com/zifer-lang/zifer/main/install.sh | bash
```

**Windows (PowerShell)**
```powershell
iwr https://raw.githubusercontent.com/zifer-lang/zifer/main/install.ps1 -useb | iex
```

Install a specific version:
```bash
curl -fsSL https://raw.githubusercontent.com/zifer-lang/zifer/main/install.sh | bash -s -- --version=0.1.0
```

## Hello, backend

```zifer
// hello.zf
server on 3000 {
    route GET "/" {
        return { message: "Hello from Zifer" }
    }
}
```

```bash
zifer run hello.zf
```

## VS Code extension

Search **"Zifer"** in the VS Code marketplace, or:
```bash
code --install-extension zifer-lang.zifer-lang
```
Or build/install it locally from `vscode-zifer/` (see its README).

## Docs

- [Getting Started](docs/getting-started.md)
- [Syntax Reference](docs/syntax.md)
- [Backend & Routing](docs/backend.md)
- [Deploying Zifer apps](docs/deploy.md)

## Benchmark (req/sec, hello-world JSON endpoint, illustrative targets)

| Runtime      | Req/sec (target) | Cold start |
|--------------|-------------------|------------|
| Zifer (native) | ~95,000          | ~5ms       |
| Go (net/http) | ~90,000           | ~5ms       |
| Node.js (express) | ~18,000       | ~60ms      |
| Python (FastAPI) | ~12,000        | ~120ms     |

> Numbers are project targets tracked in `docs/backend.md`, not yet independently benchmarked.

## License

MIT — see [LICENSE](LICENSE).
