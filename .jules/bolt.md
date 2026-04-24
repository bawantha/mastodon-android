## 2024-05-24 - Java Streams on Hot Paths
**Learning:** Java Streams (`.stream().collect()`) introduce significant allocation overhead (lambdas, collectors) on hot paths like HTML text parsing in this Android app, causing unnecessary GC pressure.
**Action:** Replace `Stream.collect(Collectors.toMap(...))` with explicit loops and early returns (e.g. `Collections.emptyMap()`) when building lookup maps for mentions/tags/emojis in performance-sensitive feed parsing code. Watch out for map collision semantics (e.g. `(a,b)->a` becomes `putIfAbsent`).
