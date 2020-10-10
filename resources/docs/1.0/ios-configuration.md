
<article class="inner-content"><section id="article" class="article-container"><h1 class="article-title"><span>iOS Configuration</span><!----></h1><div updatearticlelinks="" class="article-body"><h2 id="google-maps-key">Google Maps Key</h2>
<p>Specify your API key in the application delegate <code>ios/Runner/AppDelegate.m</code>:</p>
<pre data-lang="objectivec" class=" language-objectivec"><code class=" language-objectivec">#include "AppDelegate.h"
#include "GeneratedPluginRegistrant.h"
#import "GoogleMaps/GoogleMaps.h"

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
  [GMSServices provideAPIKey:@"YOUR KEY HERE"];
  [GeneratedPluginRegistrant registerWithRegistry:self];
  return [super application:application didFinishLaunchingWithOptions:launchOptions];
}
@end</code></pre>
<p>Or in your swift code, specify your API key in the application delegate <code>ios/Runner/AppDelegate.swift</code>:</p>
<pre data-lang="swift" class=" language-swift"><code class=" language-swift">import UIKit
import Flutter
import GoogleMaps

@UIApplicationMain
@objc class AppDelegate: FlutterAppDelegate {
  override func application(
    _ application: UIApplication,
    didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?
  ) -&gt; Bool {
    GMSServices.provideAPIKey("YOUR KEY HERE")
    GeneratedPluginRegistrant.register(with: self)
    return super.application(application, didFinishLaunchingWithOptions: launchOptions)
  }
}</code></pre>
<p>Opt-in to the preview of the embedded view by adding a boolean property to the app's <code>Info.plist</code> file with the key <code>io.flutter.embedded_views_preview</code> and the value <code>YES</code>.</p>
<ul>
<li>Click the Get dependencies or Packages get to install the libraries from <code>pubspecs.yaml</code> file.</li>
<li>Open the simulator to run iOS or Android (as the step above)</li>
<li>Then press the run button to start the project (you can still open multi simulator at the same time)</li>
</ul>
<h2 id="push-notifications">Push Notifications</h2>
<p>To integrate your plugin into the iOS part of your app, follow these steps:</p>
<ol>
<li>
<p>Generate the certificates required by Apple for receiving push notifications following <a href="https://firebase.google.com/docs/cloud-messaging/ios/certs">this guide</a> in the Firebase docs. You can skip the section titled "Create the Provisioning Profile".</p>
</li>
<li>
<p>Using the <a href="https://console.firebase.google.com/">Firebase Console</a> add an iOS app to your project: Follow the assistant, download the generated <code>GoogleService-Info.plist</code> file, open <code>ios/Runner.xcworkspace</code> with Xcode, and within Xcode place the file inside <code>ios/Runner</code>. <strong>Don't</strong> follow the steps named "Add Firebase SDK" and "Add initialization code" in the Firebase assistant.</p>
</li>
<li>
<p>In Xcode, select <code>Runner</code> in the Project Navigator. In the Capabilities Tab turn on <code>Push Notifications</code> and <code>Background Modes</code>, and enable <code>Background fetch</code> and <code>Remote notifications</code> under <code>Background Modes</code>.</p>
</li>
<li>
<p>Follow the steps in the "<a href="https://firebase.google.com/docs/cloud-messaging/ios/client#upload_your_apns_certificate">Upload your APNs certificate</a>" section of the Firebase docs.</p>
</li>
<li>
<p>If you need to disable the method swizzling done by the FCM iOS SDK (e.g. so that you can use this plugin with other notification plugins) then add the following to your application's <code>Info.plist</code> file.</p>
</li>
</ol>
<pre class=" language-xml"><code class=" hljs language-xml"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>key</span><span class="token punctuation">&gt;</span></span>FirebaseAppDelegateProxyEnabled<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>key</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>false</span><span class="token punctuation">/&gt;</span></span>
</code></pre>
<p>After that, add the following lines to the <code>(BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions</code> method in the <code>AppDelegate.m</code>/<code>AppDelegate.swift</code> of your iOS project.</p>
<h3 id="objective-c">Objective-C:</h3>
<pre class=" language-objectivec"><code class=" hljs language-objectivec">if (@available(iOS 10.0, *)) {
  [UNUserNotificationCenter currentNotificationCenter].delegate = (id&lt;UNUserNotificationCenterDelegate&gt;) self;
}
</code></pre>
<h3 id="swift">Swift:</h3>
<pre class=" language-swift"><code class=" hljs language-swift">if #available(iOS 10.0, *) {
  UNUserNotificationCenter.current().delegate = self as? UNUserNotificationCenterDelegate
}
</code></pre>
<div id="gtx-trans" style="position: absolute; left: -39px; top: 1938.91px;">
<div class="gtx-trans-icon">&nbsp;</div>
</div></div><!----><!----><article-feedback><div trans="" class="title">Was this article helpful?</div><div class="feedback-buttons"><button type="button" class="button success yes"><mat-icon role="img" svgicon="check" class="mat-icon notranslate mat-icon-no-color" aria-hidden="true"><svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" fit="" height="100%" width="100%" preserveAspectRatio="xMidYMid meet" focusable="false"><path fill="none" d="M0 0h24v24H0V0z"></path><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z"></path></svg></mat-icon><span trans="">yes</span></button><button type="button" class="button danger no"><mat-icon role="img" svgicon="close" class="mat-icon notranslate mat-icon-no-color" aria-hidden="true"><svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" fit="" height="100%" width="100%" preserveAspectRatio="xMidYMid meet" focusable="false"><path fill="none" d="M0 0h24v24H0V0z"></path><path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12 19 6.41z"></path></svg></mat-icon><span trans="">no</span></button></div><!----><!----><!----></article-feedback></section><!----></article>