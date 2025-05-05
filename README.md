
# 🧪 ASIOS™ Cross-Architecture Test Suite & Validation
[![Sponsor](https://img.shields.io/github/sponsors/asi-os?label=Sponsor&logo=github)](https://github.com/sponsors/asi-os)

Ensure feature- and performance-parity across x86_64 and ARM64.

---

## 🚀 Overview

- **CI Harness**: real and QEMU-based emulation  
- **Test Categories**  
  1. Smoke (boot, module load)  
  2. Functional (CLI/API)  
  3. Performance (MLPerf-lite, numa_io_test)  
  4. Stress & Scalability  

- **Reports**: HTML/Markdown artifacts + ANSI summaries  

---

## 📋 Prerequisites

```bash
sudo apt update
sudo apt install -y git python3-venv qemu-system-aarch64 \
  libvirt-daemon-system libvirt-clients build-essential docker.io
```

---

## 🛠️ Setup

```bash
git clone https://github.com/asi-os/asios-cross-arch.git
cd asios-cross-arch
python3 -m venv venv && source venv/bin/activate
pip install -r requirements.txt
```

Configure `configs/targets.yaml` for your test nodes.

---

## ▶️ Run Tests

- **All architectures:**  
  ```bash
  ./run_tests.sh --all
  ```
- **Single arch:**  
  ```bash
  ./run_tests.sh --arch x86_64
  ./run_tests.sh --arch arm64
  ```
- **By category:**  
  ```bash
  ./run_tests.sh --smoke
  ./run_tests.sh --perf
  ./run_tests.sh --stress
  ```
- **With report:**  
  ```bash
  ./run_tests.sh --all --report
  ```

---

## ➕ Add New Tests

1. **Script**: place in `tests/<category>/`, accept `--arch` flag.  
2. **Metadata**: add entry in the manifest YAML.  
3. **Runner**: update `run_tests.sh` and CI matrix.  
4. **Docs**: document in `docs/TESTS.md`.  
5. **PR**: include script, manifest, docs; tag the Cross-Arch Review Team.

---

## 📖 Links

- **Documentation**: [asi-os/asios-docs](https://github.com/asi-os/asios-docs)  
- **ADR**: `asios-docs/ADR/0001-cross-arch-validation.md`  
- **CI Status**: [Actions](https://github.com/asi-os/asios-cross-arch/actions)  

---

## 🤝 Contribute

- Sign the [ICLA](https://github.com/asi-os/asios-legal/blob/main/ICLA.md)  
- Add DCO sign-off on commits  
- Follow [CONTRIBUTING.md](https://github.com/asi-os/.github/blob/main/CONTRIBUTING.md) for PR guidelines  
- Join Discord: `#asios-cross-arch` → <https://discord.gg/rWuU7cWU4E>  

> © 2025 KarLex AI, Inc. — see [Legal & Governance Portal](https://asios.ai/legal)  
