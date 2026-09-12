Native Hooking Report: Apk_task1

Goal

Recover the decrypted flag that libnative-lib.so holds in memory, specifically the value returned by Java_com_example_app_Native_getSecretMessage.

Recon & Memory Notes

    Target library: libnative-lib.so

    Target function: Java_com_example_app_Native_getSecretMessage

    Return type: jstring

    Recovered flag: FLAG{jn1_n4t1v3_h00k_succ3ss_2026}

Approach

    Symbol discovery — Rather than relying on hardcoded offsets, I used Frida's Module.findExportByName to resolve the JNI export at runtime.

    Hooking — Attached an Interceptor.attach to the resolved address of the target function.

    String extraction — Inside the onLeave callback, I read the returned jstring by passing the handle into Java.vm.getEnv().getStringUtfChars(). This pulls the plaintext straight from heap memory, avoiding any issues with scope teardown or the string being collected before it could be read.

Outcome

The hook successfully captured the decrypted secret as it was returned to Java, yielding the flag above.
