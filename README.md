# AutoStock – Android app (data saved to phone storage)

Stock data is saved as a file: Documents/AutoStock/autostock.json on the phone
(it survives clearing the app cache and can be copied for backup).

## Build the APK
Needs: Node.js 18+, Android Studio (with Android SDK).

1. npm install
2. npx cap add android
3. npx cap sync
4. npx cap open android
5. In Android Studio: Build > Build Bundle(s)/APK(s) > Build APK(s)
   Install the APK from app/build/outputs/apk/debug/ on your phone
   (allow "install unknown apps").

After editing www/index.html run `npx cap sync` again.
Note: on newer Android versions, if Documents writes are refused the app still
keeps working from internal app storage.

## Build WITHOUT Android Studio (GitHub builds it for you)
1. Make a free account at github.com and create a new repository.
2. Upload every file from this project (keep the .github/workflows/build-apk.yml path;
   if the hidden .github folder does not upload, use "Add file > Create new file" on GitHub,
   type the path .github/workflows/build-apk.yml and paste that file's contents).
3. Open the Actions tab > "Build APK" > Run workflow (it also runs on every upload).
4. When it finishes (a few minutes), open the run and download "autostock-apk".
   Unzip it and install app-debug.apk on your phone.
