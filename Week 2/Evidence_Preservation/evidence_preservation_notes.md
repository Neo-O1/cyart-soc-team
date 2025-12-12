# Evidence Preservation – Notes

## 1. Goals

- Capture volatile data (memory, active network connections, running processes) before shutting systems down.
- Preserve integrity of evidence using hashing (e.g., SHA‑256).
- Maintain a clear chain of custody so any future review can trust the data.

## 2. Tools (Lab Context)

- Velociraptor: collect process lists, network connections, basic triage artifacts.
- FTK Imager (or similar): create disk images for deeper analysis.
- Hashing utilities: `sha256sum` on Linux or built‑in tools on Windows to compute hashes.

## 3. Minimal Lab Procedure

1. Note date, time, and who is collecting evidence.
2. Collect volatile data from the affected VM (connections, processes, memory if possible).
3. Save outputs to clearly named files.
4. Compute SHA‑256 hash for each evidence file.
5. Record all details in the chain‑of‑custody table.
6. Store evidence in a dedicated, write‑protected or access‑controlled location.

Even in a lab, following these steps builds good professional habits.
