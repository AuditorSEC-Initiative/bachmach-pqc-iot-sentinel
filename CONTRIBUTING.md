# Contributing to Bachmach PQC IoT Sentinel

Thank you for your interest in contributing to post-quantum IoT security!

## Ways to Contribute

- **Bug reports** — Open an issue using the Bug Report template.
- **Feature requests** — Open an issue using the Feature Request template.
- **PQC algorithm implementations** — New ML-KEM/ML-DSA variants or optimizations.
- **Hardware ports** — Support for new microcontrollers (ESP32, RP2040, STM32, etc.).
- **Benchmarks** — Add benchmark results for new hardware to `docs/pqc-benchmarks.md`.
- **Documentation** — Improve docs, tutorials, or architecture diagrams.

## Development Setup

```bash
git clone https://github.com/AuditorSEC-Initiative/bachmach-pqc-iot-sentinel
cd bachmach-pqc-iot-sentinel

# Install liboqs (required)
git clone https://github.com/open-quantum-safe/liboqs
cd liboqs && mkdir build && cd build
cmake -DOQS_USE_OPENSSL=OFF -DCMAKE_TOOLCHAIN_FILE=../esp32-toolchain.cmake ..
make -j4 bench_kem bench_sig

# Run benchmarks
./bench_kem ML-KEM-768
./bench_sig ML-DSA-65
```

## Hardware Requirements

- ESP32-S3 DevKit or RP2040 board
- USB cable for flashing
- (Optional) Logic analyzer for timing measurements

## Pull Request Process

1. Fork the repository and create a branch: `git checkout -b feat/your-feature`.
2. Make your changes with clear, atomic commits.
3. Add benchmark results if adding new hardware support.
4. Update `docs/pqc-benchmarks.md` with new measurements.
5. Submit a Pull Request against `main` with a clear description.
6. Wait for review from a maintainer (usually within 72 hours).

## Benchmark Contribution Guidelines

When adding benchmark results:
- Specify exact hardware model and revision.
- Note compiler version and optimization flags.
- Include both latency and memory measurements.
- Run each benchmark at least 3 times and report median.

## Code Style

- C/C++: Follow the existing code style (K&R indentation, 4 spaces).
- Python: PEP 8 compliant.
- Markdown: 80-character line limit preferred.

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
