# iosxdripreader

Project in development phase 

in this branch, test is done with ANE-backgroundfetch, branch performfetch-to-as, commit de5168514f5b9eb0ffc2a7ef9eb335def9c79b12
The backgroundfetch works


xdrip/xbridge reader for iOS devices

* Initial and subsequent Calibration
* Additional calibration request alerts but not the 12-hour calibration request alert
* Synchronisation to Nightscout
 * When the app is in the foreground, upload will always happen immediately after receiving a new value, also at app start, 
 * When the app is in the background, then it is iOS that decides when the app is allowed to do an upload. My initial tests have shown it starts at every 20 minutes but it goes down to every 10 minutes.
 In case you want to have the upload immediately, just keep the app in the foreground - the device will actually stay on when the app is in the foreground.


To compile :
- install Flash Builder 4.7 with FLex SDK 4.15.0, AIR 22.0 en_US
- an ios developer membership is required, full explanation : http://help.adobe.com/en_US/flex/mobileapps/WS064a3073e805330f6c6abf312e7545f65e-8000.html
- clone the repository, lets say folder iosxdripreader
- purchase license for distriqt Notifications, Dialog, Application, Message, NetworkInfo ane at http://airnativeextensions.com/
- create a folder named ane under iosxdripreader
- download the zip package, extract, and copy the file com.distriqt.BluetoothLE.ane to the folder ane
- on the site of airnativeextensions.com, create an application key, application id = net.johandegraeve.iosxdripreader (you can use another application id if you want, but then change the name also in iosxdripreader-app.xml)
- create a folder named src/distriqtkey under iosxdripreader
- create a new class in that package, DistriqtKey.as
- add a public static const distriqtKey:String = your key from distriqt
- as explained here http://airnativeextensions.com/knowledgebase/tutorial/1#ios
- donwload the ios sdk (there should be a zip corresponding to the latest ios version) and put it in a new folder under iosxdripreader
- and add it in the flash builder project properties (also explained on  http://airnativeextensions.com/knowledgebase/tutorial/1#ios)
- (explained : right click in project, properties, flex build path, native extensions, browse to the ane folder and add the new ane, then go to flex build packaging, ios, native extensions, add the file com.distriqt.BluetoothLE.ane as native extensions, check the "package" check box, also add the Apple iOS SDK that was downloaded
- in the same way as above, do this also for the Notifications, Dialog, Application, Message, NetworkInfo, AndroidSupport and core ane.
- it also uses my own ANE : https://github.com/JohanDegraeve/ANE-BackgroundFetch/tree/master/build
