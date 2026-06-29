# Grateful — Android WebView APK

Project ini siap diupload ke GitHub untuk build APK otomatis via GitHub Actions.

## Detail Aplikasi

| Item | Isi |
|---|---|
| Nama aplikasi | Grateful |
| Package ID | `com.daynite.grateful` |
| Website yang dibuka | `https://gratefulalways.netlify.app/` |
| Logo | Menggunakan file logo terlampir tanpa crop |
| Splash screen | Menggunakan logo terlampir dengan background teal |

## Struktur File

```text
grateful_android_webview_github/
├── .github/workflows/build-apk.yml
├── app/
│   ├── build.gradle
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/com/daynite/grateful/MainActivity.java
│       └── res/
├── build.gradle
├── settings.gradle
├── gradle.properties
└── README.md
```

## Cara Upload ke GitHub

1. Extract ZIP ini.
2. Buat repository baru di GitHub.
3. Upload semua file dan folder dari hasil extract.
4. Pastikan folder `.github` ikut terupload.
5. Masuk ke tab **Actions** di GitHub.
6. Pilih workflow **Build Grateful APK**.
7. Klik **Run workflow**.
8. Setelah selesai, buka bagian **Artifacts**.
9. Download file `Grateful-debug-apk`.

## Permission yang Sudah Disiapkan

Aplikasi sudah memiliki permission:

- Internet
- Network State
- Camera
- Record Audio

Camera dipakai untuk scan QR dari halaman web.

## Catatan Logo dan Splash Screen

Logo aplikasi memakai gambar terlampir dengan resize proporsional, tanpa crop.

Splash screen memakai logo yang sama dan background teal agar lebih clean saat aplikasi dibuka.

## Catatan URL

URL utama ada di:

```java
MainActivity.java
private static final String APP_URL = "https://gratefulalways.netlify.app/";
```

Jika nanti URL berubah, edit bagian tersebut lalu build ulang APK.

## Jika Kamera Tidak Terbuka

Pastikan:

1. Website memakai HTTPS.
2. Permission kamera di Android sudah diizinkan.
3. APK dibuka dari device yang punya kamera.
4. Web scanner di halaman Netlify memang meminta akses kamera.
