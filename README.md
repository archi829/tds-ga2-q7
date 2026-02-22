# Q7 Solution: GitHub Action Cache

## Objective
Create a GitHub Actions workflow that uses caching with a specific key. Create a GitHub Actions workflow in one of your repositories that uses actions/cache@v4 (or newer) to cache dependencies. Prime the cache with a key named cache-9684ed0 and include a step named prime-cache-9684ed0 that echoes the cache hit/miss result.

## Steps Taken

1.  **Workflow Creation**:
    -   Created `.github/workflows/caching.yml`.
    -   Used `actions/cache@v4`.
    -   Set cache path to `prime-numbers`.
    -   Set cache key to `cache-9684ed0`.
    -   Added step `prime-cache-9684ed0` to verify cache hits.

2.  **Repository Setup**:
    -   Initialized a new Git repository in `ga2/q7`.
    -   Added the remote: `https://github.com/archi829/tds-ga2-q7.git`.

3.  **Deployment**:
    -   Committed and pushed the workflow to the `main` branch.

4.  **Verification**:
    -   The workflow will run automatically on push.
    -   The first run will save the cache.
    -   Subsequent runs (if triggered) would restore the cache.
---
# GitHub Actions Caching Demo

This repository demonstrates how to speed up CI workflows using **GitHub Actions cache**.

## 📌 Workflow Overview

The workflow (`.github/workflows/caching.yml`) caches a folder containing generated prime numbers so that subsequent runs reuse the cached data instead of regenerating it.

## ⚙️ How It Works

1. **Checkout repository**
   Downloads the repo into the runner.

2. **Cache step (`actions/cache@v4`)**

   * Caches the `prime-numbers` directory
   * Uses key: `cache-9684ed0`
   * Exposes `cache-hit` output

3. **Generate primes (only on cache miss)**
   If cache is not found, creates:

   ```
   prime-numbers/primes.txt
   ```

4. **Echo cache result**
   Prints whether cache was hit or missed:

   ```
   Cache hit true/false
   ```

## 🚀 Expected Behavior

* **First run:** cache miss → primes generated → cache saved
* **Later runs:** cache hit → generation skipped → faster CI

## 🎯 Purpose

Shows how dependency/data caching reduces CI runtime by avoiding repeated work.

---

**Workflow file:** `.github/workflows/caching.yml`
