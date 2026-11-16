# Chordkey (APK Android)
Dibuat oleh WIMA FVNKY



## Cara 2: Build sendiri di PC

```
npm install
npx cap add android
npx @capacitor/assets generate --android
```
Lalu buka `android/app/src/main/AndroidManifest.xml` dan tambahkan dua baris ini di bawah izin INTERNET:
```
<uses-permission android:name="android.permission.RECORD_AUDIO" />
<uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS" />
```
Kemudian:
```
npx cap sync android
npx cap open android
```
Di Android Studio pilih **Build > Build Bundle(s) / APK(s) > Build APK(s)**.

## Catatan
- APK ini adalah APK debug, cukup untuk dipakai dan dibagikan langsung. Untuk Google Play Store perlu APK/AAB yang ditandatangani (signed).
- Mikrofon akan meminta izin saat pertama kali dipakai.
- Mengubah tampilan atau fitur: edit `www/index.html`, lalu build ulang.
