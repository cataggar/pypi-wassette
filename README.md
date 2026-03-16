# wassette-bin

[Wassette](https://github.com/microsoft/wassette) CLI repackaged as Python wheels for easy installation via tools like `uv`.

Wassette is a WebAssembly component runtime.

## Install

```sh
uv tool install wassette-bin
wassette --version
```

## Supported Platforms

| Platform | Wheel tag |
|----------|-----------|
| Linux x64 | `manylinux_2_17_x86_64` |
| Linux ARM64 | `manylinux_2_17_aarch64` |
| macOS x64 | `macosx_10_9_x86_64` |
| macOS ARM64 | `macosx_11_0_arm64` |
| Windows x64 | `win_amd64` |
| Windows ARM64 | `win_arm64` |

## How It Works

This package downloads the official wassette release archives from
[microsoft/wassette](https://github.com/microsoft/wassette/releases)
and repackages each `.tar.gz` / `.zip` as a platform-specific Python wheel.

A thin Python entry point (`console_scripts`) delegates to the native binary,
so `wassette` is available on `PATH` after install.

## Development

python, uv, & just are needed. Here is a quick setup example on Linux:

```bash
tdnf install -y python3 python3-pip
python3 -m pip install uv
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc && source ~/.bashrc
uv tool install rust-just
```

## License

This package redistributes wassette under its
[MIT](https://github.com/microsoft/wassette/blob/main/LICENSE) license.
