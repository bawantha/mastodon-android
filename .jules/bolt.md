## 2024-04-05 - Avoid Java Streams on Android Hot Paths
**Learning:** Java Streams (e.g., `.stream().collect()`) introduce significant overhead from lambda allocations and collectors on Android, especially for small collections on hot paths.
**Action:** Use explicit loops and early returns instead of Streams for collection processing on Android hot paths to avoid performance degradation.
