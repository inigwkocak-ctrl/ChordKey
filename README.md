# Chordkey (APK Android)
Dibuat oleh WIMA FVNKY

## Cara 1: Tanpa install apa pun (pakai GitHub, gratis)
1. Buat akun di github.com, lalu buat repository baru (boleh private).
2. Upload SEMUA isi folder ini ke repository (termasuk folder .github, www, dan assets).
3. Buka tab **Actions**, pilih **Build APK**, klik **Run workflow**.
4. Tunggu sekitar 5 menit sampai centang hijau. Buka run itu, lalu download **Chordkey-apk** di bagian Artifacts.
5. Unzip, kirim `app-debug.apk` ke HP Android, buka, izinkan "Install dari sumber tidak dikenal", lalu install.

## Cara 2: Build sendiri di PC
Butuh Node.js 18+ dan Android Studio (sudah termasuk Android SDK dan JDK 17).
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
