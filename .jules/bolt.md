## 2025-01-20 - Java Stream vs Explicit Loop overhead
**Learning:** Java Streams in Android (`stream().collect(...)`) can add significant object allocation overhead on hot paths, like `HtmlParser.java` text parsing which runs for every post.
**Action:** Replace small collection stream operations with explicit `for` loops and `Collections.emptyMap()` for early returns to save memory and CPU on hot paths.
