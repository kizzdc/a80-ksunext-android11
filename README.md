# Galaxy A80 (r1q) — KernelSU Next, Android 11

## Device confirmation (photo supplied by device owner)

- Model: **SM-A805F**
- One UI: **3.1**, Android **11**
- PDA: **A805FXXU7DWE3** (Android 11, binary 7)
- Baseband: **A805FXXU7DWE2**
- Running kernel: **4.14.190**, dated 2023-05-12
- CSC: XID
- Samsung firmware bulletin: https://doc.samsungmobile.com/SM-A805F/008854190828/eng.html

## Critical safety note

This repository contains an **experimental compile test** only.
The initial reference source `kkmmee94/android_kernel_sm6150_unified` (`btf7-fire`) is
a Galaxy A80 Android **10**, Linux **4.14.117** source.
It is **not verified** for the owner's Android **11** / 4.14.190 stock firmware.

**DO NOT FLASH any build artifact from the reference-source experiments.**

We need the Samsung Open Source Release Center kernel archive for **SM-A805F**
corresponding to **Android 11 / A805FXXU7DWE3**, or another source with
verifiable firmware compatibility. Search https://opensource.samsung.com/
for `SM-A805F`; download and inspect the applicable Android 11 source.
Keep an original AP/boot image from the same firmware for future packaging and rollback.

## Samsung source found (owner's screenshot, 2026-10-16)

- Samsung Open Source Release Center result: **SM-A805F**, version **A805FXXU7DXE1**.
- Listed package name: `SM-A805F_EUR_RR_Opensource.zip`.
- Samsung's release notes confirm **A805FXXU7DXE1 is Android 11**; it is newer than the owner's **A805FXXU7DWE3**.
- **Not yet downloaded or inspected:** exact kernel patch level, defconfig, compiler requirements, stock Android 11 boot image compatibility.
- Wait for the source archive and compare with the owner's Android 11 firmware before making a flash image.

## Running the diagnostic workflow

Open **Actions → A80 KernelSU Next - experimental build**. Runs are now manual-only until matched Android 11 source is integrated.
On first test leave `enable_ksu=false`.
Inspect the logs and the artifact `a80-kernel-inspection-<run>`.
A successful compilation **does not** mean a bootable or flashable kernel.
KernelSU Next should be integrated only after source/defconfig/toolchain baseline
and compatibility checks.

## Next milestones

1. Obtain and verify the Android 11 Samsung kernel source for this exact A80 firmware.
2. Compile the unmodified Android 11 source using the correct toolchain.
3. Integrate KernelSU Next legacy support on this non-GKI kernel; verify required
   Kconfig options and build.
4. Inspect the device boot image and device tree; package a test image with a
   known-good backup and a recoverable flash procedure.
5. Test boot and KernelSU Next manager support on the device.

This repository does not yet contain a validated Odin/TWRP flash file.
