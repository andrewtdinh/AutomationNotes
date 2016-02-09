***********************************
Do not install anything with the sudo command
***********************************
Install XCode if not already installed on your computer.  To check:

$ xcode-select -p 
(If you see something like "/Applications/Xcode.app/Contents/Developer", then XCode was already installed. )

If Xcode was not installed, install it from Apple's App Store --> Apple App Store

Install Command Line Tools if not installed:

$ gcc --help

If Command Line Tools are installed you will see the help file for gcc displayed.
If you don't have Command Line Tools, a pop-up will open prompting you to install it

Set up Java Development Kit:
Download jdk-7u80-macosx-x64.dmg from this link (http://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html#jdk-7u80-oth-JPR) (You might have to set up an account to download it)

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddav1caa44a260cc96d66ce4077d61110fae.png

Install the jkd with the default settings
Now, at your termina console:

$ cd
Copy the following line into your .bash_profile and save:
export JAVA_HOME=`/usr/libexec/java_home -v 1.7`

Close and restart the terminal console.  Then check what java version you have:

$ java -version
(Confirm that you get version 1.7.0_80 or 1.8.0_66)

Download Android Studio from this link.  (developer.android.com/sdk/index.html)
 Installing Android Studio:
Launch the downloaded .dmg file
Drag and drop it into your Application folder and eject from devices in finder.
Open Android Studio
Start a new project
 Follow the set up wizard, keeping to the default settings.  For project name, just use anything.

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddav054a48d7b6ecb18ce4a56ccd992bf5b6.png

Select Blank Activity
Set up an Android Virtual Device:
Tools > Android > AVD Manager > Click on create virtual device
Select Galaxy Nexus as the device

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddav1221ce8dfa32a8dbda252f80186d7e9c.png

For system image, click the download link for KitKat, API Level 19, x86
After it is downloaded, click Next
Name your AVD "Galaxy_Nexus_API_19" and finish
Click on the play icon to start your device to make sure it is usable.

Setting up the SDK Manager:
Tools > Android > SDK Manager.  You will see which platform you have installed
Check mark all boxes starting with Android 4.4.2 and up and click OK button.  This will install all platforms starting with API level 19 and up on your computer.  By the end you will see the below screen:

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddav3fdb5df75eedeac1cf46cd4456c51f96.png

Set up ANDROID_HOME:
Open up your terminal console

$ cd

Open up .bash_profile with your favorite editor and paste in these lines:

export ANDROID_HOME=/Users/<daneez>/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
(replace <daneez> with your username, of course)

Restart terminal and type:   

> echo $ANDROID_HOME  
(That should display the path to Android Home - /users/<user>/Library/Android/sdk)

> adb
(adb should now work)

Installing Homebrew:

Open your terminal console and type:

$ brew

If Homebrew was not installed:

$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Install npm and node:

$ brew install node

You can test your installation using these commands at the terminal:

$ node -v
$ npm -v

Downloading simulators in Xcode through the app:
Launch Xcode
Install additional required components
Xcode > Preferences in the menu on top left corner.  Then click on the Downloads tab.
Click on the little arrows to the right of the iOS 8.4, 9.1, 9.0, or whichever simulator to download the simulator (you might have to provide your password to authorize the download).


Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddav5c6a89cd5069fb5b7f49777837096790.png


Installing Appium (to use on command line):
$ npm install -g appium
(Check your installation using the command below)
$ appium --version

Installing Appium GUI:
Download a copy of appium-1.4.13 or a later version (.dmg) from Appium Bit Bucket

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > BitBucket.png

Install it by searching for it in firefox or safari (download does not work in Chrome) and add it to the Applications folder
Open the app
Click on General Settings icon and uncheck the Check For Updates checkbox:

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddavea59234f78342f63df462c8e18a53d0d.png

Click on the stethoscope icon to run Appium doctor.  Make sure all the checks are okay.

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddavafaa3804d3d450c826c0249151ba5afe.png

Setting up for Android testing:
Click on the Android icon to open up the Android settings
Do the followings:
Set App Path to:  https://s3.amazonaws.com/breakthrough-mobile-builds/development/breakthrough-production.apk
Checkmark App Path.
Checkmark 'Stop on Reset'
Checkmark 'Launch AVD' and select 'Galaxy_Nexus_API_19'
Checkmark 'Device Name'
Platform Name:  Android
Automation Name:  Appium
Platform Version:  4.4 KitKat (API Level 19)

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddavf41530b945d956f5afe5b842ecc0065c.png

Click on radio button underneath the Android button.   Now click the 'Launch' button and wait a few seconds.
Click on the Magnifier Glass icon.  Wait for a few seconds and your Android Virtual Device (AVD) will launch, download the apk and automatically launch the app.
Once the AVD and app are successfully launched, close the AVD and click on 'Stop' button.

Setting up for iOS testing:
Click on the Apple icon and do the following:
Checkmark 'App Path' and enter into the field 'https://s3.amazonaws.com/breakthrough-mobile-builds/development/breakthrough-ios-dev.zip'
Checkmark 'Force Device' and select iPhone 6
Select 8.4 as the Platform Version
Checkmark 'Show Simulator Log'

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > NewBasiciOSSettings.png

Click on the 'Advanced' tab and do the following:
Checkmark 'Use Native Instrument Library' and 'Instruments Launch Timeout'

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddavc35b55c008ff724598462ac25fae8998.png

Launching the inspector to test the settings:
Click on the radio button underneath the Apple icon to select it, then click the 'Launch' button
Wait a few seconds and click on the Magnifier Glass icon.  Wait a little bit for your iPhone simulator to launch and install the app.
Once your iPhone simulator and app are launched, you can close the simulator and click 'Stop'.
Click on the radio button underneath the Android icon to select it, then click the 'Launch' button
Wait a few seconds and click on the Magnifier Glass icon.  Wait a little bit for your Android Virtual Device (AVD) to launch and install the app.
Once your AVD and app are launched, you can close the AVD and click 'Stop' on the Appium GUI.

Congrats!!!  You have successfully set up Appium for inspecting the app on Android and iOS.

Test running mobile automation in RubyMine:
Clone the mobile automation code for BT

$ git clone git@github.com:BreakthroughBehavioralInc/qa_mobile.git

Open the project in RubyMine and click on the link to install any missing gems.
Open qa_mobile > spec > spec_helper.rb and make sure the platform is 'android' and the server_location is 'local'

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddavdab6b0873f58ae21a4b421386c208226.png

Open qa_mobile > config > appium_config > android > appium.txt and change to the below:

Andrew Dinh > Andrew's Appium & XCode Set up on Mac > worddav22a6b2c6b7d20bfdad145bdf369450fe.png

Now, open qa_mobile > spec > login > login_spec.rb
In the terminal console, launch the appium server by typing:

$ appium (then press 'Enter')

Right click on the spec 'should be able to login with ph+c1' and run it (the first Run option)
