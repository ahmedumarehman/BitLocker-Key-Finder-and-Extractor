# BitLocker Key Finder and Extractor

A Digital Forensics project developed to simulate the forensic process of locating and extracting cryptographic keys associated with BitLocker-encrypted drives.

The project provides a graphical interface that combines multiple forensic operations, including searching for BitLocker recovery key files, processing memory dumps, capturing live RAM, and extracting the BitLocker Volume Master Key (VMK).

> **Academic Project:** Developed as part of the Digital Forensics course (CY2002) at FAST National University of Computer & Emerging Sciences, Islamabad Campus.

---

## Table of Contents

- [Overview](#overview)
- [Project Objective](#project-objective)
- [Features](#features)
- [How the Project Works](#how-the-project-works)
- [Workflow](#workflow)
- [Components](#components)
- [GUI Features](#gui-features)
- [BitLocker Recovery Key Search](#bitlocker-recovery-key-search)
- [Memory Dump Analysis](#memory-dump-analysis)
- [Volume Master Key Extraction](#volume-master-key-extraction)
- [WinHex Integration](#winhex-integration)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Forensic Workflow](#forensic-workflow)
- [Project Structure](#project-structure)
- [Important Notes](#important-notes)
- [Limitations](#limitations)
- [Educational Purpose](#educational-purpose)
- [References](#references)
- [Author](#author)

---

## Overview

BitLocker is a full-volume encryption technology used by Windows to protect data stored on drives.

From a digital forensics perspective, investigating a BitLocker-encrypted volume can require locating available recovery keys or encryption-related material from different sources.

This project was developed as a tool to simulate and simplify parts of this forensic workflow.

The application provides a graphical interface through which an investigator can:

1. Search a selected volume or directory for BitLocker recovery key files.
2. Search using different search methods.
3. Copy potentially relevant files to an output directory.
4. Process an existing RAM/memory dump.
5. Capture a live RAM image.
6. Search memory for BitLocker-related keys.
7. Launch an external forensic disk-decryption utility for Volume Master Key extraction.
8. Inspect files and their hexadecimal representation using WinHex.

---

## Project Objective

The primary objective of this project is to demonstrate how different sources can be used during a forensic investigation of a BitLocker-encrypted system.

The project focuses on three main areas:

### 1. File-Based Key Discovery

The application searches a selected partition or directory for files that may contain BitLocker recovery information.

### 2. Memory-Based Key Discovery

The application can process an existing memory dump or capture live RAM and use the resulting memory image as a source for locating encryption keys.

### 3. Volume Master Key Extraction

The project provides an interface option for launching Elcomsoft Forensic Disk Decryptor to extract the BitLocker Volume Master Key (VMK) from a memory image.

---

## Features

### BitLocker Key File Search

The application can search a selected volume or directory for BitLocker-related files.

Available search options include:

- File Name Search
- UTF-16LE String Search
- Exhaustive Search
- Copy responsive files to the output directory

The original project documentation demonstrates searches for `.TXT` and `.BEK` files.

---

### Memory Dump Processing

The application allows an investigator to select an existing RAM image/memory dump and process it for BitLocker-related key material.

This is useful when a memory image has already been acquired as part of a forensic investigation.

---

### Live RAM Capture

The application integrates with:

```text
winpmem_mini_x64_rc2.exe
```
