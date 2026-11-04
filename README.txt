BILLING SOFTWARE - ANDROID APP (APK)
====================================
This is the phone app for the Billing Software v9.26+.  It shows the same phone screens as the browser version
(billing, items, customers, dues, reports, chat, voice calls) but as a real installed app, and it connects to the
computer by scanning a QR code.  It is NOT a separate program: the data stays on the computer.

HOW THE QR CONNECTION WORKS
  * The computer (Settings > Mobile Access) shows a "Android app" QR.  It holds the computer's address AND the
    fingerprint of the shop's own security certificate.
  * The app scans it, downloads the certificate from the computer, and checks that it matches the fingerprint in
    the QR.  From then on the app trusts ONLY that certificate - no "install certificate" steps on the phone.
  * You sign in with the same user name / password as the program (nothing is stored inside the QR).
  * Phone and computer must be on the same WiFi (or the same Tailscale network).

PHONE: Android 10 or newer.

BUILD THE APK (choose ONE way)
  A) Android Studio (easiest on a Windows PC)
     1. Install Android Studio (free).   2. File > Open > choose this BillingApp folder, wait for "Gradle sync".
     3. Build > Build Bundle(s) / APK(s) > Build APK(s).
     4. Click "locate": the file is  app\build\outputs\apk\debug\app-debug.apk   -> rename it BillingSoftware.apk
  B) GitHub (no installation): create a free GitHub repository, upload this folder's contents, open the
     Actions tab > "Build Android APK" > Run workflow.  Download "BillingSoftware-apk" when it finishes.

INSTALL ON PHONES
  * Easiest: copy BillingSoftware.apk into the program folder   assets\mobile\   on the computer, restart the
    program, switch Mobile Access ON.  Settings > Mobile Access then shows a small QR: scan it with the phone
    camera to download the app, open the downloaded file, allow "install unknown apps" when Android asks.
  * Or send the APK file to the phone (WhatsApp, USB, Drive) and open it.
  * Open the app, press "Scan QR code", scan the big "Android app" QR on the computer.  Done.

CHANGE COMPUTER / SCAN AGAIN:  press the phone's Back button on the first screen > "Scan a new QR code".

NOTES
  * This build is signed with Android's debug key: fine for your own shop phones.  For the Play Store you
    would need your own signing key (Build > Generate Signed Bundle / APK).
  * Voice calls: the app asks for the microphone the first time.
  * PDF bills open in the phone's PDF viewer / share sheet.  WhatsApp / phone links open the phone's own apps.
