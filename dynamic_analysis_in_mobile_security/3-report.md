Revealing and Invoking Hidden Functions Report: Apk_task3

Goal

Find the flag-decryption routines left unlinked inside Apk_task3.apk, bring the required class dependencies to life at runtime with Frida, and run the app's secondary custom decoding transforms to recover the hidden flag.

Findings

    Target class: com.example.app.SecretUtils

    Decryption methods: decryptFlag(String) and decodeBase64Custom(String)

    Recovered flag: FLAG{h1dd3n_m3th0d_inv0k3d_3xp0s3d_2026}

Approach

    Static analysis — Decompiled the APK with jadx and located com.example.app.SecretUtils, spotting methods that are never reached through the app's normal UI flow.

    Dynamic instantiation — Used Frida's Java.use() wrapper along with the $new() constructor syntax to instantiate SecretUtils directly inside the Android runtime process memory.

    Invocation & decoding — Called decryptFlag() with the expected input to produce an intermediate Base64 string, then fed that result into decodeBase64Custom() to reverse the byte-level XOR obfuscation and reveal the plaintext flag.

Outcome

By invoking the dormant methods manually, the custom decode chain unwound cleanly and produced the flag above.
