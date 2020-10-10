- [Run & Build](#section-3)

<a name="section-3"></a>
<section id="article" class="article-container"><h1 class="article-title"><span>Run &amp; Build</span><!----></h1><div updatearticlelinks="" class="article-body"><h2 id="run-the-application">Run the Application</h2>
<p>1- In the target selector, select an Android device for running the app. If none are listed as available, select Tools&gt; Android &gt; AVD Manager and create one there. For details, see <a href="https://developer.android.com/studio/run/managing-avds" target="_blank" rel="noopener">Managing AVDs</a>.</p>
<p>Click the run icon in the toolbar, or invoke the menu item Run &gt; Run. Locate the main Android Studio toolbar: <img src="https://support.smartersvision.com/storage/article_images/NoVMEEPJMPovnXdVFdfxJYsOyLAssNuVWqw8YfmK.png"></p>
<p>2- If you don't use <strong>Android Studio or IntelliJ</strong> you can use the command line to run your application using the following command</p>
<pre data-lang="" class=" language-none"><code>flutter run</code></pre>
<h2 id="build-and-install-app">Build and Install App</h2>
<p>1- After you make all your changes and customizations save all your project, Open the console, navigate to your project folder and execute the following command to build your app</p>
<pre data-lang="" class=" language-none"><code>flutter build apk --release</code></pre>
<p>If you are deploying the app to the Play Store, it's recommended to use app bundles or split the APK to reduce the APK size.<br>To generate an app bundle, run:</p>
<pre data-lang="" class=" language-none"><code>flutter build appbundle --target-platform android-arm,android-arm64,android-x64</code></pre>
<p>Learn more on <a href="https://developer.android.com/guide/app-bundle" target="_blank" rel="noopener">https://developer.android.com/guide/app-bundle</a><br>To split the APKs per ABI, run:</p>
<pre data-lang="" class=" language-none"><code>flutter build apk --target-platform android-arm,android-arm64,android-x64 --split-per-abi</code></pre>
<p>Learn more on <a href="https://developer.android.com/studio/build/configure-apk-splits#configure-abi-split" target="_blank" rel="noopener">https://developer.android.com/studio/build/configure-apk-splits#configure-abi-split</a></p>
<p>You should get the APK file in the <code>build/output/apk</code> folder, to install your application on your connected device run the following command</p>
<pre data-lang="" class=" language-none">flutter install</pre>
<p>2- If you want to upload your application on Google Play you must sign it before uploading, generate a signing key by running the following command:</p>
<pre data-lang="" class=" language-none"><code class="lang- language-none">keytool -genkey -v -keystore android/app/key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias key</code></pre>
<p>3- Open <code>/android/key.properties</code> and edit the following attributes after that re-build your application:</p>
<pre data-lang="" class=" language-none"><code class="lang- language-none">storePassword=&lt;Your Key Password&gt;
keyPassword=&lt;Your Key Password&gt;
keyAlias=key
storeFile=key.jks</code></pre></div><!----><!----></section>