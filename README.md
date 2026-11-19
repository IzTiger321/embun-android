# Embun Android

Android app for Embun. It is a thin shell that loads https://embun-theta.vercel.app.
Web updates reach the app automatically on the next launch, so you do not need
to publish a new APK for web changes. Publish a new APK only when native
plugins or Android permissions change.

## 1. Clone the repository

```bash
git clone https://github.com/<your-user>/embun-android.git
cd embun-android
npm install
```

## 2. Build the APK

**Option A: GitHub Actions (no Android Studio needed)**

1. Push to `main`.
2. Open the **Actions** tab, select **Build Embun APK**.
3. When the run finishes, download the `embun-debug-apk` artifact.

**Option B: Local build**

1. Install Android Studio and JDK 17.
2. Run:
   ```bash
   npx cap add android
   npx cap sync android
   npx cap open android
   ```
3. In Android Studio choose **Build > Build APK(s)**.

## 3. Install on your phone

1. Copy `app-debug.apk` to the phone.
2. Allow installs from unknown sources for your file manager.
3. Open the APK and install.

## 4. Updates

No action needed. The app always loads the latest web version.

## 5. Changing the web address

Edit `server.url` in `capacitor.config.json`, then run `npx cap sync android`.

## Notes

- Sign-in and the vault work the same as the web app.
- If the phone is offline, the offline page shows a Retry button.
