# Project Setup
---


##Installing Software

In order to get started with Flutter, we have to install some software on your local machine. You can either use macOS, Windows or Linux to get started with Flutter, however, macOS has the benefit of getting both the iOS and Android environment on the same machine. We will assume that you are using macOS for Flutter development, but you can always follow the similar instructions for Windows and Linux as well.

<strong>See this section to install required softwares:</strong><br />

[Flutter Setup - Windows](/docs/{{route}}/{{version}}/flutter-setup-windows)


##Use Flutter Doctor
Flutter comes up with an awesome command line utility to check if your machine is set up for local development. Flutter has Flutter Doctor command which guides developers through setting up the local development environment for both iOS and Android. Flutter Doctor inspects which tools are installed on the local machine and which tools need to be configured. Once the Flutter Doctor command is happy, we can carry on creating a new Flutter app.


##Setting up Editors
Flutter development can be done on any editor or IDE of your choice. The getting started guide for Flutter contains detailed information on IDE setup for , IntelliJ and . However, you can use lightweight editors like Sublime Text for Flutter development as well. The choice of editor/IDE is completely up to the developer. Once we have finished the setup for our favourite editor, we can start developing Flutter apps.

##Know Pub Package Manager
Flutter uses the  to manage the Dart packages inside the Flutter project. You will find the pubspec.yaml file in the Flutter project which imports Dart dependencies inside the Flutter project. You can mention all the dependencies in the file and install using the command:

<pre data-lang="" class=" language-none"><code class="lang- language-none">$ flutter pub get</code></pre>
This will install all the dependencies and create a locked version of the file, which is pubspec.lock, so that we will always lock dependencies. We can upgrade the dependencies using the command:


<pre data-lang="" class=" language-none"><code class="lang- language-none">$ flutter package upgrade</code></pre>
This will upgrade all packages to the latest version, or you can update individual packages.

It's good to know the concept of Pub Package Manager well in advance in order to understand the Flutter project better.

##Project Structure
See the project directory Structure
<img src="https://soloarc.store/public/assets/project-struct.png">
