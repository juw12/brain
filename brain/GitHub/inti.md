---
title: "inti"
type: note
date: 2026-11-10
tags:
  - github
  - project/inti
  - status/active
  - public
repo: "https://github.com/juw12/inti"
visibility: public
updated: 2026-11-18
source: github-sync
claim: "Built Inti: a from-scratch capability microkernel OS in Rust for 32-bit x86 that boots in a browser tab and restarts a crashed or hung driver while the system keeps running, with files on its disk that survive a restart; emulator only, not verified"
role: author
evidence: [https://github.com/juw12/inti]
publish: true
---

# inti

> A small capability-based microkernel OS for 32-bit x86, written from scratch in Rust. Boots in a browser tab; a crashed or hung driver is restarted while the system keeps running, and files on its disk survive a restart. Emulator only, not verified.

- **Repo:** https://github.com/juw12/inti (public)
- **Live:** https://juw12.github.io/inti/ · landing: https://juw12.github.io/p/inti/
- **Language:** Rust (no_std, no alloc crate), x86 assembly boot sector, Python build and test tools
- **Topics:** capability-based-security, fault-tolerance, kernel, microkernel, no-std, operating-system, osdev, rust, v86, x86
- **Started:** 2026-11-10

## What it does

- Its own boot sector (no GRUB, no multiboot), a capability microkernel of 2,933 lines of Rust with 22 system calls, and device drivers that run as ordinary programs.
- A supervisor restarts a driver that crashes or stops answering. In QEMU the screen driver answered again 50.7 ms after a crash and 708.1 ms after a hang (median of 5 runs, guest clock).
- Files that survive a restart (new in 0.2.0), kept by a disk driver that is itself an ordinary program. In QEMU, 60 random power cuts left 0 broken volumes.
- No ambient authority: every system call starts from a capability. A hostile program holding one capability made 51 attempts on the kernel, the hardware and other programs in QEMU, and all 51 were denied.
- The kernel has no heap; the kernel, boot sector and programs hold 88 uses of `unsafe`, each with a written justification. A fuzz run of 1,000,769 random system calls from 2,283 tasks in QEMU ended with 0 invariant violations in 4,653 checks.
- The browser demo boots the same disk image, byte for byte, in v86, with buttons that crash a driver, hang the file server, run the hostile program and fuzz the kernel.

## Notes

- A small research system, not a usable one: emulators only (QEMU and v86), never started on a real computer, no network, one processor. Storage is one volume of at most 4 MiB (48 files, one namespace, the primary ATA channel in PIO mode); in the browser demo files last until the page is reloaded. Its programs are a handful of small ones.
- Not formally verified (seL4 is). W^X is enforced only where the processor has the no-execute bit and has only been shown in emulators; no IOMMU, revocation takes back all copies or none, and the supervisor is trusted with everything.
- None of the ideas is new: MINIX 3 restarts user-mode drivers, seL4 is a capability kernel with proofs, Redox is a microkernel system in Rust, and they work at real scale. The request was "the best in the world"; Inti is not that, and its README says so.
- Evidence: `python build.py gates` gave 9 of 9 gates on 2026-11-17, and `tools/check_claims.py` recomputes the numbers in the documents. The fuzz button was not exercised in the live browser check; the other demo commands were.

## Updates

- 2026-11-10: built from scratch, 9/9 gates, published with a browser demo, landing page, profile bullet and portfolio card · 2026-11-10 2120 inti hone
- 2026-11-11: round 2 (W^X through PAE and NX, failure-path tests, guided tour) built and judged: 9/9 gates, pairwise won, gain under the minimum, so not kept; loop stopped on plateau; candidate in draft pull request [#1](https://github.com/juw12/inti/pull/1) · 2026-11-11 0256 inti hone
- 2026-11-12: round 3 (the kernel's own source checked on the build machine: model, bounded exploration, mutants) built and judged: 9/9 gates, pairwise won, mean 8.2 against 8.1125, gain under the minimum, so not kept; loop stopped on plateau; candidate in draft pull request [#2](https://github.com/juw12/inti/pull/2), stacked on #1 · 2026-11-12 0106 inti hone
- 2026-11-12: rounds 4 (processor shares, less authority for init, single serial writer) and 5 (tests for round 4's mutant holes, a fresh mutant sample) built and judged: 9/9 gates, pairwise won, means 8.25 and 8.1875 against 8.1125, gains under the minimum, so neither kept; loop stopped on its limit of 5 rounds; candidates in draft pull requests [#3](https://github.com/juw12/inti/pull/3) and [#4](https://github.com/juw12/inti/pull/4), stacked on #2 · 2026-11-12 1806 inti hone
- 2026-11-12: second run, round 6 (checks for round 5's eleven mutant holes, a fourth mutant sample, the surviving mutants booted in QEMU, Miri cut short) built and judged: 9/9 gates, pairwise won, mean 8.2625 against 8.1125, gain under the minimum, so not kept; stopped on the session limit; candidate in draft pull request [#5](https://github.com/juw12/inti/pull/5), stacked on #4 · 2026-11-12 2341 inti hone
- 2026-11-13: second run, round 7 (timing failures measured, a fifth mutant sample, the survivors booted twice each in QEMU with 4 of 21 caught on the same check, a launch race in two tests corrected, Miri cut short) built and judged: 9/9 gates, pairwise won, mean 8.1425 against a bar of 8.4125 (two of three judges answered), not kept; the run stopped on plateau; candidate in draft pull request [#6](https://github.com/juw12/inti/pull/6), stacked on #5 · 2026-11-13 1618 inti hone

- 2026-11-13, later: on the owner's instruction `main` now holds round 7 (commit `b112a23`). Pull requests #1 to #6 are merged, the demo page serves the round 7 image (live files match the checkout), and the old `main` is kept as tag `backup-main-before-r7` on the remote. By the loop's keep rule none of rounds 2 to 7 was kept; the kept score stays 7.95.
- 2026-11-16: product round 1 (a disk driver as an ordinary program, files that survive a restart, a machine matrix of 10 QEMU machines, pages on storage, hardware and programs): 9/9 gates, merged as [#7](https://github.com/juw12/inti/pull/7), released as v0.2.0; no judged score this round · 2026-11-16 1608 inti hone
- 2026-11-17: product round 2 (share check sets noisy measurements aside, planted-fault time limit no longer counts as a catch, banner version, all evidence re-run): 9/9 gates, merged as [#8](https://github.com/juw12/inti/pull/8), released as v0.2.1; share check still fails about 7 % of runs as "could not measure"; no judged score this round · 2026-11-17 0434 inti hone
- 2026-11-18: product round 3 (a display server with a desktop of 640 by 480 pixels, a terminal and up to 6 program windows, a mouse, background programs; all evidence re-run): 9/9 gates, merged as [#9](https://github.com/juw12/inti/pull/9), released as v0.3.0; emulators only, keyboard goes to the terminal only; no judged score this round · 2026-11-18 0304 inti hone
