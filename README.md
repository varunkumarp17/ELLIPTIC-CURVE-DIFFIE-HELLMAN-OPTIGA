# ECDH Key Exchange Using OPTIGA™

## Overview

This project demonstrates how to perform **Elliptic Curve Diffie–Hellman (ECDH) key exchange** using an **Infineon OPTIGA™ secure element** (OPTIGA Trust M / Trust X).

The private key is **securely generated and stored inside the OPTIGA chip** and **never leaves the device**. The shared secret is derived inside the secure element, providing strong protection against key extraction and side-channel attacks.

---

## What is ECDH?

ECDH (Elliptic Curve Diffie–Hellman) is a cryptographic protocol that allows two parties to establish a **shared secret** over an insecure channel.

- Each side has a **private key**
- Each side exchanges **public keys**
- Both compute the same **shared secret**
- The shared secret is typically used to derive symmetric keys (AES, HMAC, etc.)

---

## Why Use OPTIGA?

Using OPTIGA provides:

- 🔐 Hardware-protected private keys
- 🚫 Private keys never exposed to host MCU
- 🛡️ Certified secure element (Common Criteria)
- ⚡ Hardware-accelerated ECC operations

---

## Supported Curves

Commonly supported curves include:

- `secp256r1` (NIST P-256) ✅ **recommended**
- `secp384r1` (device dependent)

---

## Prerequisites

### Hardware
- OPTIGA Trust M / Trust X
- Supported MCU (STM32, ESP32, etc.)
- I²C interface connected to OPTIGA

### Software
- OPTIGA Trust Middleware
- C compiler
- Host OS: Linux / Windows / Embedded RTOS

---

## High-Level ECDH Flow

1. Initialize OPTIGA application
2. Generate ECC key pair inside OPTIGA
3. Export public key
4. Receive peer public key
5. Compute shared secret inside OPTIGA
6. Use shared secret for key derivation

---

## Key Storage

- **Private Key**: Stored in OPTIGA key slot (OID)
- **Public Key**: Exportable
- **Shared Secret**: Returned to host or stored securely

Example key OID:
- `0xE0F1` – ECC private key slot

---

