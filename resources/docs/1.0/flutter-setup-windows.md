# How to Setup Flutter in Windows
---

How to Setup Flutter in Android Studio/VS Code – Windows

Download Android Studio – https://developer.android.com/studio/

Download VS Code – https://code.visualstudio.com/download

Get the Flutter SDK – https://flutter.dev/docs/get-started/install

Learn more about Android Studio – https://developer.android.com/studio/intro/



### Step 1 : Get the Flutter SDK

1. Download the following installation bundle to get the latest stable release of the Flutter SDK

1. Extract the zip file and place the contained flutter in the desired installation location for the Flutter SDK >(for example, C:\SDKs\flutter; do not install Flutter in a directory like C:\Program Files\ that requires elevated privileges).

"Note: Since we are using flutter SDK version > 1.20.x it already includes DART sdk no need to intall dart sdk."

### Step 2 : Update your path

If you wish to run Flutter commands in the regular Windows console, take these steps to add Flutter to the PATH environment variable:
From the Start search bar, enter ‘env’ and select Edit environment variables for your account.
Under User variables check if there is an entry called Path:

> If the entry exists, append the full path to C:\SDKs\flutter\bin using ; as a separator from existing values.

> If the entry doesn’t exist, create a new user variable named Path with the full path to C:\SDKs\flutter\bin as its value.

"Important:
Note that you have to close and reopen any existing console windows for these changes to take effect.
You are now ready to run Flutter commands in the Flutter Console!"

### Step 3 : Run flutter doctor

From a console window that has the Flutter directory in the path (see above), run the following command to see if there are any platform dependencies you need to complete the setup:

<code>C:\src\flutter>flutter doctor</code><br>
If you find any issue during environment setup, please go online [Click here](https://flutter.dev/docs/get-started/install/windows)
