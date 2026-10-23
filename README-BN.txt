ডিজিটাল সেবা — Premium V5

নতুন পরিবর্তন
1) অ্যাপ/ওয়েব background বা অন্য app/tab-এ গেলে unlocked session সঙ্গে সঙ্গে lock হবে। ফিরে এলে PIN লাগবে।
2) Online login server-এর live PIN দিয়ে যাচাই হয়। সফল online login-এর পর এই trusted device-এ PIN-এর SHA-256 hash রাখা হয়, তাই internet না থাকলেও সঠিক PIN দিয়ে cached হিসাব দেখা যায়। PIN plain text হিসেবে browser storage-এ রাখা হয় না।
3) PIN response UI উন্নত: checking spinner, ভুল PIN-এ inline error + shake, সফল PIN-এ success state। Enter key-ও কাজ করে।
4) Dashboard-এ মোট হিসাব cards এবং নিট হিসাব আগে; compact তারিখ filter তার নিচে।
5) Dashboard date filter mobile-এ ছোট ও দুই কলামে fit হয়; calendar picker আগের মতো আছে।
6) PWA icon ঠিক করার জন্য আলাদা ANY এবং MASKABLE icon দেওয়া হয়েছে। Maskable icon-এ logo safe-zone-এর মধ্যে center করা হয়েছে।
7) হিসাব, offline queue, Google Sheet sync, category badge, বাংলা digit normalize, dd/mm/yy display আগের মতো রাখা হয়েছে।

ফাইল
- index.html
- Code.gs
- manifest.json
- service-worker.js
- favicon.png
- icon-192.png
- icon-512.png
- icon-192-maskable.png
- icon-512-maskable.png

UPDATE
1) Apps Script-এ Code.gs replace করুন (backend logic একই V4 compatible)।
2) Deploy > Manage deployments > Edit > New version > Deploy.
3) website folder-এ সব V5 file upload করুন।
4) পুরনো installed PWA icon cache থাকলে app uninstall করে browser site data/cache clear করে আবার install করলে নতুন centered icon নিশ্চিতভাবে দেখা যাবে।
5) প্রথমে online login করুন, তারপর offline lock/unlock test করুন।

নিরাপত্তা
- Recovery PIN backend Code.gs-এ server-side থাকে। Apps Script project edit access কাউকে দেবেন না।
- এটি ছোট ব্যবসার PIN gate; ব্যাংক/enterprise authentication নয়।
