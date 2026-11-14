# সেটআপ (Flutter)

1. Flutter ইনস্টল করুন: https://docs.flutter.dev/get-started/install
2. টার্মিনালে: `flutter create --org com.yourname --project-name doc_scanner .`
   (এই ফোল্ডারের ভেতরে চালান; আমার `pubspec.yaml` ও `lib/main.dart` রেখে দিন/আবার বসান)
3. `android/app/build.gradle` এ `minSdk = 21` (বা `minSdkVersion 21`) করুন।
4. `android/app/src/main/AndroidManifest.xml` এর `<application>` ট্যাগের ভেতরে বসান:
   ```xml
   <meta-data
       android:name="com.google.android.gms.ads.APPLICATION_ID"
       android:value="ca-app-pub-3940256099942544~3347511713"/>
   ```
   (এটা টেস্ট ID। নিজের AdMob App ID দিয়ে বদলান)
5. `flutter pub get` তারপর ফোন কানেক্ট করে `flutter run`
6. Play Store-এর জন্য: `flutter build appbundle --release`
7. `lib/main.dart` এ `kBannerId` নিজের Banner Ad Unit ID দিয়ে বদলান।

---
# কম্পিউটার ছাড়া APK বানানোর সহজ উপায় (GitHub Actions)
1. github.com এ বিনা খরচে অ্যাকাউন্ট খুলে নতুন Repository বানান।
2. এই ফোল্ডারের সব ফাইল (`.github` ফোল্ডারসহ) আপলোড করুন।
3. Actions ট্যাব > "Build Android APK" > Run workflow।
4. ৫-১০ মিনিট পর "app-files" ডাউনলোড করুন। ভেতরে `app-release.apk` (ফোনে ইনস্টল) ও `app-release.aab` (Play Store) পাবেন।
