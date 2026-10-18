# হাজিরা ও খরচ - অ্যান্ড্রয়েড অ্যাপ (APK) বানানোর নিয়ম

এই ফোল্ডারটি GitHub-এ তুললেই GitHub নিজে APK বানিয়ে দেবে। কোনো কম্পিউটার প্রোগ্রাম লাগবে না।

## ধাপ ১: ওয়েব অ্যাপের লিংক ঠিক করুন
Apps Script-এ Deploy করার সময় এই দুটো ঠিক থাকতে হবে:
- Execute as: **Me**
- Who has access: **Anyone**

তারপর যে লিংকটা পাবেন (শেষে `/exec` থাকে) সেটা কপি করে রাখুন।

## ধাপ ২: লিংক বসানো
`app/src/main/res/values/strings.xml` ফাইল খুলুন। `app_url` লাইনের লেখাটা মুছে আপনার লিংক বসান:

    <string name="app_url" translatable="false">https://script.google.com/macros/s/xxxxxxxx/exec</string>

## ধাপ ৩: GitHub-এ তোলা
1. github.com এ লগইন করে **New repository** চাপুন, নাম দিন `hajira-app`, **Create repository** চাপুন।
2. **uploading an existing file** লিংকে চাপুন।
3. এই ফোল্ডারের **ভেতরের সবকিছু** (`.github` ফোল্ডারসহ) টেনে এনে ছাড়ুন। 
   (`.github` লুকানো ফোল্ডার হতে পারে - ফোনে/পিসিতে "hidden files দেখান" চালু করুন।)
4. নিচে **Commit changes** চাপুন।

## ধাপ ৪: APK বানানো
1. রিপোজিটরির **Actions** ট্যাবে যান।
2. "APK বানানো" চাপুন, তারপর **Run workflow** চাপুন (আপনি ফাইল তুললে নিজে নিজেও চালু হয়)।
3. ৩-৫ মিনিট অপেক্ষা করুন, সবুজ টিক এলে ঐ রানটিতে চাপুন।
4. নিচে **Artifacts** এর **hajira-apk** চাপলে zip নামবে। zip খুললে `app-debug.apk` পাবেন।

## ধাপ ৫: ফোনে বসানো
1. `app-debug.apk` ফোনে পাঠান (WhatsApp / Google Drive)।
2. ফাইলে চাপ দিন। "অজানা উৎস থেকে ইনস্টল" এর অনুমতি চাইলে অনুমতি দিন।
3. ইনস্টল হলে "হাজিরা ও খরচ" নামে অ্যাপ পাবেন।

## জেনে রাখুন
- ওয়েব অ্যাপের কোড (Code.gs / Index.html) বদলালে APK আবার বানাতে হবে না - শুধু Apps Script-এ নতুন ভার্সন Deploy করুন।
- লিংক বদলালে (নতুন Deploy করলে) শুধু ধাপ ২ করে আবার APK বানান।
- PDF ডাউনলোড করলে ফাইল ফোনের **Downloads** ফোল্ডারে যাবে।
- Android 10 বা তার উপরের ফোনে চলবে।
