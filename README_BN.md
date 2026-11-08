# Rahul Hardware — সংশোধিত Demo App Package

এই প্যাকেজে সেটিংস মেনুর layout-shift সমস্যা ঠিক করা ও পুনরায় যাচাই করা HTML অ্যাপ রয়েছে।

## ফাইল
- `index.html` — সংশোধিত ওয়েব অ্যাপের মূল কোড।
- `manifest.webmanifest` — PWA পরিচিতি।
- `service-worker.js` — HTTPS hosting-এ offline cache; cache version v2 করা হয়েছে।
- `assets/` — অ্যাপ আইকন।
- `APP_BUILDER_PROMPT_BN_EN.md` — অন্য AI/App Builder-এ দেওয়ার পূর্ণ prompt।
- `SOURCE_CHECK.txt` — এই সংস্করণে করা পরীক্ষার সারাংশ।

## চালানো / Install
1. ZIP extract করুন।
2. ফোল্ডারটি HTTPS hosting-এ publish করুন।
3. Android Chrome-এ সাইট খুলে menu থেকে **Install app** বা **Add to Home screen** বেছে নিন।

শুধু HTML ফাইল খুললে PWA install বা service worker offline cache কাজ নাও করতে পারে।

## গুরুত্বপূর্ণ সীমাবদ্ধতা
এটি HTML/PWA starter; Android APK/AAB নয়। APK করতে Capacitor বা Trusted Web Activity/Android Studio build, signing এবং বাস্তব ডিভাইস পরীক্ষা লাগবে। ডেটা একই browser/device-এর local storage-এ থাকে; cloud sync, login/PIN, multi-device sync নেই। Restricted preview-তে browser storage বন্ধ থাকলে demo session-memory fallback ব্যবহার করবে, তখন reload-এর পর data থাকবে না। বাস্তব হিসাব ব্যবহারের আগে backup নিন এবং নিজে যাচাই করুন।
