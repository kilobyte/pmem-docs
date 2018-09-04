# PMEM and BLK Modes

The NFIT \(**N**VDIMM **F**irmware **I**nterface **T**able\) specification defined by the [ACPI v6.0](http://www.uefi.org/sites/default/files/resources/ACPI_6_0_Errata_A.PDF) standardizes not only the description of Persistent Memory \(PMEM\) and Block \(BLK\) modes, but also

## LIBNVDIMM Sub-System

The Linux LIBNVDIMM subsystem provides support for three types of NVDIMMs; PMEM, BLK, and NVDIMM.  PMEM \(Persistent Memory\) devices allow byte addressable access.  BLK \(block\) devices allow sector atomicity like traditional storage devices.  NVDIMM devices can simultaneously support both PMEM



1. **PMEM \(nd\_pmem.ko\):** Drives a system-physical-address range.  This range is contiguous in system memory and may be interleaved \(hardware
2. **BLK \(nd\_blk.ko\):** This driver performs I/O using a set of platform

## Differences between PMEM and BLK Modes

While PMEM provides direct byte-addressable CPU-load/store access to


