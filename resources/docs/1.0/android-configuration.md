
- [Android Configuration](#section-3)

<a name="section-3"></a>
<section id="article" class="article-container"><h1 class="article-title"><span>Android Configuration</span><!----></h1><div updatearticlelinks="" class="article-body"><h2 id="icons">Icons</h2>
<p>1- Create your app icon <code>ic_launcher</code> and notification icon <code>ic_notification</code> folders <a href="https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html" target="_blank" rel="noopener">How to generate an app icon?</a> after you generate icons folder replace the following folders:</p>
<ul>
<li><code>/mipmap-hdpi</code> in <code>/android/app/src/main/res/</code> folder</li>
<li><code>/mipmap-mdpi</code> in <code>/android/app/src/main/res/</code> folder</li>
<li><code>/mipmap-xhdpi</code> in <code>/android/app/src/main/res/</code> folder</li>
<li><code>/mipmap-xxhdpi</code> in <code>/android/app/src/main/res/</code> folder</li>
<li><code>/mipmap-xxxhdpi</code> in <code>/android/app/src/main/res/</code> folder</li>
</ul>
<div class="widget widget-note">
<div class="title">Note:</div>
Must rename app icon <code>ic_launcher</code> and notification icon <code>ic_notification</code></div>
<h2 id="get-dependencies">Get Dependencies</h2>
<p>And just run the following command</p>
<pre data-lang="" class=" language-none"><code class="lang- language-none">flutter pub get</code></pre>
<h2 id="change-package-name">Change Package Name</h2>
<p>If you want to change the package name following the next steps</p>
<p>1 - Open <code>/android/app/build.gradle</code> and change the package name</p>
<pre data-lang="json" class=" language-json"><code class=" language-json">    defaultConfig {
        applicationId "&lt;REPLACE WITH YOUR PACKAGE NAME&gt;" // this is the package name
        minSdkVersion 21
        targetSdkVersion 33
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
    }</code></pre>
<p>2- Open <code>/android/app/src/main/AndroidManifest.xml</code> , <code>/android/app/src/profil/AndroidManifest.xml</code>, <code>/android/app/src/debug/AndroidManifest.xml</code> and specify your:</p>
<ul>
<li><strong><em>Y</em>OUR PACKAGE NAME</strong></li>
<li><strong> YOUR APPLICATION NAME</strong></li>
<li><strong>YOUR GOOGLE MAPS KEY</strong></li>
</ul>
<div class="widget widget-note">

<pre data-lang="xml" class=" language-xml"><code class=" language-xml"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>manifest</span> <span class="token attr-name"><span class="token namespace">xmlns:</span>android</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>http://schemas.android.com/apk/res/android<span class="token punctuation">"</span></span>
    <span class="token attr-name">package</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>&lt;YOUR PACKAGE NAME&gt;<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>

    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>uses-permission</span> <span class="token attr-name"><span class="token namespace">android:</span>name</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>android.permission.INTERNET<span class="token punctuation">"</span></span><span class="token punctuation">/&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>uses-permission</span> <span class="token attr-name"><span class="token namespace">android:</span>name</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>android.permission.ACCESS_FINE_LOCATION<span class="token punctuation">"</span></span><span class="token punctuation">/&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>uses-permission</span> <span class="token attr-name"><span class="token namespace">android:</span>name</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>android.permission.ACCESS_COARSE_LOCATION<span class="token punctuation">"</span></span><span class="token punctuation">/&gt;</span></span>

    <span class="token comment">&lt;!-- io.flutter.app.FlutterApplication is an android.app.Application that
         calls FlutterMain.startInitialization(this); in its onCreate method.
         In most cases you can leave this as-is, but you if you want to provide
         additional functionality it is fine to subclass or reimplement
         FlutterApplication and put your custom class here. --&gt;</span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>application</span>
        <span class="token attr-name"><span class="token namespace">android:</span>name</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>.Application<span class="token punctuation">"</span></span>
        <span class="token attr-name"><span class="token namespace">android:</span>label</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>&lt;YOUR APPLICATION NAME&gt;<span class="token punctuation">"</span></span>
        <span class="token attr-name"><span class="token namespace">android:</span>icon</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>@mipmap/ic_launcher<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>

        <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>meta-data</span> <span class="token attr-name"><span class="token namespace">android:</span>name</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>com.google.android.geo.API_KEY<span class="token punctuation">"</span></span>
                   <span class="token attr-name"><span class="token namespace">android:</span>value</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>&lt;YOUR GOOGLE MAPS KEY&gt;<span class="token punctuation">"</span></span><span class="token punctuation">/&gt;</span></span></code></pre>
<p>3 - Open <code>/android/app/src/main/kotlin/&lt;Your Package name folders&gt;/Application.kt</code> and change the package name same thing with <code>/android/app/src/main/kotlin/&lt;Your Package name folders&gt;/MainActivity.kt</code></p>
</section>