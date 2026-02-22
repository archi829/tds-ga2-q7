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
    -   Configured git identity (aloktripathi1 / aloktripathe@gmail.com).
    -   Committed and pushed the workflow to the `main` branch.

4.  **Verification**:
    -   The workflow will run automatically on push.
    -   The first run will save the cache.
    -   Subsequent runs (if triggered) would restore the cache.
