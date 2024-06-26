# fetch_llama_cpp

This Python module automates downloading and setting up the latest and best
binary distribution of `llama.cpp` for your system and graphics card
(if present).

It fetches the latest release from GitHub, detects your system's
specifications, and selects the most suitable binary for your setup.

## Features

- **Automatic Detection**: Detects your operating system, architecture,
    and GPU (NVIDIA or AMD).
- **CUDA Compatibility**: Checks for CUDA and driver versions to ensure
    compatibility.
- **AVX Support**: Checks for AVX, AVX2, and AVX512 support on your CPU.
- **Download and Extraction**: Downloads the appropriate binary and
    extracts it.
- **Verification**: Runs the binary with `--version` to verify the setup.

## Requirements

- Python 3.x
- `requests` library
- `cpuinfo` library
- `zipfile` and `tarfile` modules
- `subprocess` and `platform` modules

## Usage

There are several ways to run fetch_llama_cpp:

**1. As a module**

```bash
% python3 -m fetch_llama_cpp
```

**2. As a script**

```bash
% python3 fetch_llama_cpp.py
```

**3. As an import**

```python
import fetch_llama_cpp

fetch_llama_cpp.fetch()
```

**4. As a container**

```bash
% podman run -v $PWD:/app fetch_llama_cpp
% docker run -v $PWD:/app fetch_llama_cpp
```

## Environment

fetch_llama_cpp is designed to be run in a Python 3 environment:

**POSIX (Linux, macOS, etc.)**:

```bash
% python -m venv .venv
% source ./.venv/bin/activate
(.venv) % pip install -r requirements.txt
(.venv) % ./fetch_llama_cpp.py
```

**Windows**:

```bash
> python -m venv .venv
> .\.venv\Scripts\avtivate.ps1
> pip install -r requirements.txt
> python fetch_llama_cpp.py
```

## How It Works

1. **Fetch Latest Release**: The script fetches the latest release information
    from the `llama.cpp` GitHub repository.
2. **System Information**: It detects your operating system and architecture.
3. **GPU Detection**: Checks for NVIDIA or AMD GPUs and their respective CUDA
    and driver versions.
4. **AVX Support**: Checks if your CPU supports AVX, AVX2, or AVX512.
5. **Select Best Asset**: Based on the detected information, it selects the
    most suitable binary asset.
6. **Download and Extract**: Downloads the selected binary and extracts it to
    the specified directory.
7. **Run Verification**: Runs the binary with `--version` to ensure it was set
    up correctly.

## Notes

- Ensure you have the necessary permissions to run `nvidia-smi` and `lspci`
    commands.
- The script assumes a standard directory structure for the downloaded and
    extracted files.

## License

This project is licensed under the MIT License.
