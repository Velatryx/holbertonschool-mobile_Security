Network Interception & Cryptographic Decryption Report: Apk_task2

Goal

Capture the encrypted HTTPS traffic flowing between Apk_task2.apk and its backend, defeat the app's dynamic SSL pinning, recover the symmetric key and IV through decompilation, and decrypt the flag carried in transit.

Findings & Crypto Parameters

    Interception setup: Burp Suite Community / Objection

    Pinning bypass: Runtime instrumentation using Frida / Objection's android sslpinning disable

    Cipher in use: AES/CBC/PKCS5Padding

    Key: 321c_s3cr3t_k3y!

    IV: 1234567890abcdef

    Recovered flag: Holberton{keystore_is_not_as_safe_as_u_think!}
Approach

    Traffic capture & pinning bypass — Installed the Burp Suite CA on the test device and used Objection to disable the app's OkHttp/TrustManager pinning, allowing HTTPS traffic to be proxied and inspected.

    Decompilation — Loaded the APK into jadx-gui and traced the response handling logic to com.example.cryptoapp.network.CryptoManager.

    Key/IV recovery — Pulled the hardcoded AES-128 key and IV constants directly from the decompiled source.

    Decryption — Base64-decoded the server response payload and ran it through AES-CBC offline to recover the hidden plaintext flag.

Outcome

With pinning neutralized and the crypto parameters in hand, the intercepted response decrypted cleanly to the flag above.
