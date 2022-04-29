# SITA
The main production project has three folders: ChildVoiceRecognition, SITA(SrDes2020), and SITA. The ChildVoiceRecognition folder is for experimental voice processing. The SrDes2020 is from the senior design team that handled this project in 2020. It is the 2020 version of the project with miscellaneous code snippets. The main production project is SITA which contains all the relevant files and folders that the team has worked on. 

The Sita folder is divided into three different folders: Assets, Packages, Project Settings. 
## Assets: contains the folders that include most of the UI and backend files. ParentLock, Recorder, Settings, etc. Most of the code that the team worked on is in the Assets folder. 
## Packages: contains all of the necessary packages that are created by Unity to assist in building SITA. 
## ProjectSettings: contains files that shape SITA’s user interface. It determines how things are placed, sized, and formatted within the application. Ideally, you will be editing the user interface directly in Unity, and the changes will automatically be reflected in these files upon saving.

## Assets: 
- ArrabicSupport.cs: This is an Open Source File Created by: Abdullah Konash. This File allows the users to use Arabic text in XNA and Unity platform. It flips the characters and replaces them with the appropriate ones to connect the letters in the correct way.
- ArabicSupport.cs.meta: Contains the metadata for the ArabicSupport video file. 
- FontAwesomeSVGs.meta: Contains the metadata for the font
- Global.meta: Contains the metadata in the app.
- PlayTime.meta: Contains the metadata for playtime.
- Plugins.meta: Contains the metadata for the plugins. 
- Scenes.meta: Contains the metadata for the scene files in the app.
- StreamingAssets.meta: Contains the metadata for the streaming assets of the app. 
- TextMesh Pro.meta: Contains the metadata for the text in the app.
- XR.meta: Contains the metadata. 
- appIcon.meta: Contains the metadata for the icons found in the app. 
### FontAwsomeSVGs: all images and icons used in SITA (like the Settings icon)
- Arrow-alt-circle-left.svg: image in the folder for the arrow that points left. 
- Arrow-alt-circle-left.svg.meta: metadata in the folder for the arrow that points left. 
- Home.svg: the home icon image in the folder.
- Home.svg.meta: the metadata in the folder for the home icon image . 
- icons8-play-30.png: the play icon image in the folder.
- icons8-play-30.png.meta: the metadata in the folder for the play icon image. 
- Play-button-image-background-arts-symbol-sign-tape-road-sign-transparent-png-2172104.png: The play button icon image in the folder. 
- Play-button-image-background-arts-symbol-sign-tape-road-sign-transparent-png-2172104.png.meta: the metadata in the folder for the play icon image. 
- Question-circle.svg: the question circle icon image for help in the folder.
- Question-circle.svg.meta: the metadata in the folder for the question icon image. 
- Star.svg: the star icon image in the folder.
- Star.svg.meta: the metadata in the folder for the star icon image. 
- Sun.svg.meta: the sun icon image in the folder.
- Sun.svg.meta: the sun icon metadata in the folder.
### Global: all information that is shared across SITA (algorithm files, scenes manager, etc). 
- Envelope.cs: Envelope file for the speech recognition algorithm. It has a Class for storing RMS envelope history from buffers. It Saves buffer's envelope samples, princesses samples, handles full chunks, saves that envelope, goes to the next envelope sample and resets the chunk state. It then unwraps the envelope and normalizes the sample. 
- Envelope.cs.meta: The metadata in the folder for the envelope.cs file. 
- GlobalTimer.cs:  returns the number of midnights passed since the date stored in the LastDateChildsCornerOpen PlayerPref. Resets the DailyChildTime PlayerPref to 0, called when midnight is passed.
- GlobalTimer.cs.meta: The metadata in the folder for the global timer.cs file. 
- ManageScenes.cs: Simple class for calling SceneManager Methods via GameObjects.
- Managescenes.cs.meta: The metadata in the folder for the mange scenes.cs file. 
- MessageBox.cs: Displays the message in the box, and is the driver code for the messagebox.prefab file. The message box is for user and error warnings. 
- MessageBox.prefab: The prefab file for the message box for errors and warnings. 
- MessageBox.prefab.meta: The metadata in the folder for the message box file.
- SceneManager.prefab: Prefab file for Unity for the scene manager. 
- SceneManager.prefab.meta: The metadata for the scene manager file. 
- Speech.cs: The main speech file in the app. Controls and handles the functions with the volume in the app. It converts between decibel and linear scales, and gets accuracy using minimum error. Accuracy normalized to a max in range [0.0f,1.0f], normalizes a buffer (for audio samples). It also normalizes positives, and handles min and max normalization for analytical signals in range [0,1]. Takes care of sliding window error in the volume and normalizes the error to 1. 
- Speech.cs.meta: The metadata in the global folder for the speech file.  
- SpeechParams.cs: Static class for storing global speech processing variables.
- SpeechParams.cs.meta: The metadata in the global folder for the speech params file.
### Playtime: all the  information about game rewards
- Audio.meta: The metadata file for the audio in the app. 
### Plugins: additional plugins needed to help build and run SITA. 
- Android.meta: The metadata in the plugins folder for android installation. 
### Android: Android folder. 
- AndroidManifest.xml: xml file in the android folder for the android build. 
- AndroidManifest.xml.meta: The metadata in the android folder for the android build.  
- NativeCamera.meta: The metadata in the plugins folder for the native camera used to record videos from the therapist and upload them. 
### NativeCamera: The native camera folder in the app. This plugin helps you take pictures/record videos natively with your device's camera on Android & iOS.
1. ABOUT
This plugin helps you take pictures/record videos natively with your device's camera on Android & iOS.

2. HOW TO
NativeCamera no longer requires any manual setup on Android. If you were using an older version of the plugin, you need to remove NativeCamera's "<provider ... />" from your AndroidManifest.xml.

For reference, the legacy documentation is available at: https://github.com/yasirkula/UnityNativeCamera/wiki/Manual-Setup-for-Android

2.2. iOS Setup
There are two ways to set up the plugin on iOS:

2.2.a. Automated Setup for iOS
- (optional) change the value of CAMERA_USAGE_DESCRIPTION in Plugins/NativeCamera/Editor/NCPostProcessBuild.cs

2.2.b. Manual Setup for iOS
- set the value of ENABLED to false in NCPostProcessBuild.cs
- build your project
- enter a Camera Usage Description to Info.plist in Xcode
- insert "-framework MobileCoreServices -framework ImageIO" to the "Other Linker Flags" of Unity-iPhone Target

3. FAQ
- Can't use the camera, it says "Can't find ContentProvider, camera is inaccessible!" in Logcat
After building your project, verify that NativeCamera's "<provider ... />" tag is inserted in-between the "<application>...</application>" tags of PROJECT_PATH/Temp/StagingArea/AndroidManifest.xml. If not, please contact me.

- Can't use the camera, it says "java.lang.ClassNotFoundException: com.yasirkula.unity.NativeCamera" in Logcat
If you are sure that your plugin is up-to-date, then enable "Custom Proguard File" option from Player Settings and add the following line to that file: -keep class com.yasirkula.unity.* { *; }

4. SCRIPTING API
Please see the online documentation for a more in-depth documentation of the Scripting API: https://github.com/yasirkula/UnityNativeCamera

enum NativeCamera.Permission { Denied = 0, Granted = 1, ShouldAsk = 2 };
enum NativeCamera.Quality { Default = -1, Low = 0, Medium = 1, High = 2 };
enum NativeCamera.ImageOrientation { Unknown = -1, Normal = 0, Rotate90 = 1, Rotate180 = 2, Rotate270 = 3, FlipHorizontal = 4, Transpose = 5, FlipVertical = 6, Transverse = 7 }; // EXIF orientation: http://sylvana.net/jpegcrop/exif_orientation.html (indices are reordered)

delegate void CameraCallback( string path );

//// Accessing Camera ////

// This operation is asynchronous! After user takes a picture or cancels the operation, the callback is called (on main thread)
// CameraCallback takes a string parameter which stores the path of the captured image, or null if the operation is canceled
// maxSize: determines the maximum size of the returned image in pixels on iOS. A larger image will be down-scaled for better performance. If untouched, its value will be set to SystemInfo.maxTextureSize. Has no effect on Android
// saveAsJPEG: determines whether the image is saved as JPEG or PNG. Has no effect on Android
// preferredCamera: determines whether the rear camera or the front camera should be opened by default
NativeCamera.Permission NativeCamera.TakePicture( CameraCallback callback, int maxSize = -1, bool saveAsJPEG = true, PreferredCamera preferredCamera = PreferredCamera.Default );

// quality: determines the quality of the recorded video
// maxDuration: determines the maximum duration, in seconds, for the recorded video. If untouched, there will be no limit. Please note that the functionality of this parameter depends on whether the device vendor has added this capability to the camera or not. So, this parameter may not have any effect on some devices
// maxSizeBytes: determines the maximum size, in bytes, for the recorded video. If untouched, there will be no limit. This parameter has no effect on iOS. Please note that the functionality of this parameter depends on whether the device vendor has added this capability to the camera or not. So, this parameter may not have any effect on some devices
NativeCamera.Permission NativeCamera.RecordVideo( CameraCallback callback, Quality quality = Quality.Default, int maxDuration = 0, long maxSizeBytes = 0L, PreferredCamera preferredCamera = PreferredCamera.Default );

bool NativeCamera.DeviceHasCamera(); // returns false if the device doesn't have a camera. In this case, TakePicture and RecordVideo functions will not execute

bool NativeCamera.IsCameraBusy(); // returns true if the camera is currently open. In that case, another TakePicture or RecordVideo request will simply be ignored


Runtime Permissions: 

Accessing the camera is only possible when the permission state is Permission.Granted. TakePicture and RecordVideo functions request permission internally (and return the result) but you can also check/request the permissions manually
NativeCamera.Permission NativeCamera.CheckPermission();
NativeCamera.Permission NativeCamera.RequestPermission();
 If the permission state is Permission.Denied, user must grant the necessary permission(s) manually from the Settings (Android requires Storage and, if declared in AndroidManifest, Camera permissions; iOS requires Camera permission). These functions help you open the Settings directly from within the app
void NativeCamera.OpenSettings();
bool NativeCamera.CanOpenSettings();


 Utility Functions:

// Creates a Texture2D from the specified image file in correct orientation and returns it. Returns null, if something goes wrong
// maxSize: determines the maximum size of the returned Texture2D in pixels. Larger textures will be down-scaled. If untouched, its value will be set to SystemInfo.maxTextureSize. It is recommended to set a proper maxSize for better performance
// markTextureNonReadable: marks the generated texture as non-readable for better memory usage. If you plan to modify the texture later (e.g. GetPixels/SetPixels), set its value to false
// generateMipmaps: determines whether texture should have mipmaps or not
// linearColorSpace: determines whether texture should be in linear color space or sRGB color space
Texture2D NativeCamera.LoadImageAtPath( string imagePath, int maxSize = -1, bool markTextureNonReadable = true, bool generateMipmaps = true, bool linearColorSpace = false );

// Creates a Texture2D thumbnail from a video file and returns it. Returns null, if something goes wrong
// maxSize: determines the maximum size of the returned Texture2D in pixels. Larger thumbnails will be down-scaled. If untouched, its value will be set to SystemInfo.maxTextureSize. It is recommended to set a proper maxSize for better performance
// captureTimeInSeconds: determines the frame of the video that the thumbnail is captured from. If untouched, OS will decide this value
// markTextureNonReadable: see LoadImageAtPath
Texture2D NativeCamera.GetVideoThumbnail( string videoPath, int maxSize = -1, double captureTimeInSeconds = -1.0, bool markTextureNonReadable = true );

// Returns an ImageProperties instance that holds the width, height and mime type information of an image file without creating a Texture2D object. Mime type will be null, if it can't be determined
NativeCamera.ImageProperties NativeCamera.GetImageProperties( string imagePath );

// Returns a VideoProperties instance that holds the width, height, duration (in milliseconds) and rotation information of a video file. To play a video in correct orientation, you should rotate it by rotation degrees clockwise. For a 90-degree or 270-degree rotated video, values of width and height should be swapped to get the display size of the video
NativeCamera.VideoProperties NativeCamera.GetVideoProperties( string videoPath );
### (Folder)- Android, Editor, iOS. 
- Android.meta: The metadata for the android native camera in the folder. 
- Editor.meta: The medata for the editor in the app. 
- NativeCamera.Runtime.asmdef: Native camera runtime file.
- NativeCamera.Runtime.asmdef.meta: The metadata file for the native runtime file. 
- NativeCamera.cs: The cs file for the native camera installed on the phone and lets the app connect the camera to the app. 
- NativeCamera.cs.meta: The metadata file in the folder for the native camera.
- iOS.meta: the iOS metadata file in the folder. 
### Native Gallery: 

1. ABOUT
This plugin helps you interact with Gallery/Photos on Android & iOS.


2. HOW TO
for Android: set "Write Permission" to "External (SDCard)" in Player Settings
for iOS: there are two ways to set up the plugin on iOS:

a. Automated Setup for iOS
- (optional) change the values of PHOTO_LIBRARY_USAGE_DESCRIPTION and PHOTO_LIBRARY_ADDITIONS_USAGE_DESCRIPTION in Plugins/NativeGallery/Editor/NGPostProcessBuild.cs
- (Unity 2017.4 or earlier) if your minimum Deployment Target (iOS Version) is at least 8.0, set the value of MINIMUM_TARGET_8_OR_ABOVE to true in NGPostProcessBuild.cs

b. Manual Setup for iOS
- set the value of ENABLED to false in NGPostProcessBuild.cs
- build your project
- enter a Photo Library Usage Description to Info.plist in Xcode
- also enter a "Photo Library Additions Usage Description" to Info.plist in Xcode, if exists
- set Info.plist's "Prevent limited photos access alert" property's value to 1 in Xcode, if exists
- insert "-weak_framework PhotosUI -weak_framework Photos -framework AssetsLibrary -framework MobileCoreServices -framework ImageIO" to the "Other Linker Flags" of Unity-iPhone Target (if your Deployment Target is at least 8.0, it is sufficient to insert "-weak_framework PhotosUI -framework Photos -framework MobileCoreServices -framework ImageIO")
- lastly, remove Photos.framework and PhotosUI.framework from Link Binary With Libraries of Unity-iPhone Target in Build Phases, if exists

IMPORTANT: If you are targeting iOS 14 or later, you need to build your app with Xcode 12 or later to avoid any permission issues.


3. FAQ
- How can I fetch the path of the saved image or the original path of the picked image on iOS?
You can't. On iOS, these files are stored in an internal directory that we have no access to (I don't think there is even a way to fetch that internal path).

- Android build fails, it says "error: attribute android:requestLegacyExternalStorage not found" in Console
"android:requestLegacyExternalStorage" attribute in AndroidManifest.xml fixes a rare UnauthorizedAccessException on Android 10 but requires you to update your Android SDK to at least SDK 29. If this isn't possible for you, you should open NativeGallery.aar with WinRAR or 7-Zip and then remove the "<application ... />" tag from AndroidManifest.xml.

- Can't access the Gallery, it says "java.lang.ClassNotFoundException: com.yasirkula.unity.NativeGallery" in Logcat
If you are sure that your plugin is up-to-date, then enable "Custom Proguard File" option from Player Settings and add the following line to that file: -keep class com.yasirkula.unity.* { *; }

- Nothing happens when I try to access the Gallery on Android
Make sure that you've set the "Write Permission" to "External (SDCard)" in Player Settings.

- NativeGallery functions return Permission.Denied even though I've set "Write Permission" to "External (SDCard)"
Declare the WRITE_EXTERNAL_STORAGE permission manually in your Plugins/Android/AndroidManifest.xml file as follows: <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" tools:node="replace"/>
You'll need to add the following attribute to the '<manifest ...>' element: xmlns:tools="http://schemas.android.com/tools"

- Saving image/video doesn't work properly
Make sure that the "filename" parameter of the Save function includes the file's extension, as well


4. SCRIPTING API
Please see the online documentation for a more in-depth documentation of the Scripting API: https://github.com/yasirkula/UnityNativeGallery

enum NativeGallery.PermissionType { Read = 0, Write = 1 };
enum NativeGallery.Permission { Denied = 0, Granted = 1, ShouldAsk = 2 };
enum NativeGallery.ImageOrientation { Unknown = -1, Normal = 0, Rotate90 = 1, Rotate180 = 2, Rotate270 = 3, FlipHorizontal = 4, Transpose = 5, FlipVertical = 6, Transverse = 7 }; // EXIF orientation: http://sylvana.net/jpegcrop/exif_orientation.html (indices are reordered)
enum MediaType { Image = 1, Video = 2, Audio = 4 };

delegate void MediaSaveCallback( bool success, string path );
delegate void NativeGallery.MediaPickCallback( string path );
delegate void MediaPickMultipleCallback( string[] paths );

//// Saving Media To Gallery/Photos ////

// On Android, your images/videos are saved at DCIM/album/filename. On iOS 14+, the image/video will be saved to the default Photos album (i.e. album parameter will be ignored). On earlier iOS versions, the image/video will be saved to the target album.
// NOTE: Make sure that the filename parameter includes the file's extension, as well
// IMPORTANT: NativeGallery will never overwrite existing media on the Gallery. If there is a name conflict, NativeGallery will ensure a unique filename. So don't put '{0}' in filename anymore (for new users, putting {0} in filename was recommended in order to ensure unique filenames in earlier versions, this is no longer necessary).
// MediaSaveCallback takes "bool success" and "string path" parameters. If the image/video is saved successfully, success becomes true. On Android, path stores where the image/video was saved to (is null on iOS). If the raw filepath can't be determined, an abstract Storage Access Framework path will be returned (File.Exists returns false for that path)
NativeGallery.Permission NativeGallery.SaveImageToGallery( byte[] mediaBytes, string album, string filename, MediaSaveCallback callback = null );
NativeGallery.Permission NativeGallery.SaveImageToGallery( string existingMediaPath, string album, string filename, MediaSaveCallback callback = null );
NativeGallery.Permission NativeGallery.SaveImageToGallery( Texture2D image, string album, string filename, MediaSaveCallback callback = null );
NativeGallery.Permission NativeGallery.SaveVideoToGallery( byte[] mediaBytes, string album, string filename, MediaSaveCallback callback = null );
NativeGallery.Permission NativeGallery.SaveVideoToGallery( string existingMediaPath, string album, string filename, MediaSaveCallback callback = null );


//// Retrieving Media From Gallery/Photos ////

// This operation is asynchronous! After user selects an image/video or cancels the operation, the callback is called (on main thread)
// MediaPickCallback takes a string parameter which stores the path of the selected image/video, or null if nothing is selected
// MediaPickMultipleCallback takes a string[] parameter which stores the path(s) of the selected image(s)/video(s), or null if nothing is selected
// title: determines the title of the image picker dialog on Android. Has no effect on iOS
// mime: filters the available images/videos on Android. For example, to request a JPEG image from the user, mime can be set as "image/jpeg". Setting multiple mime types is not possible (in that case, you should leave mime as is). Has no effect on iOS
NativeGallery.Permission NativeGallery.GetImageFromGallery( MediaPickCallback callback, string title = "", string mime = "image/*" );
NativeGallery.Permission NativeGallery.GetVideoFromGallery( MediaPickCallback callback, string title = "", string mime = "video/*" );
NativeGallery.Permission NativeGallery.GetImagesFromGallery( MediaPickMultipleCallback callback, string title = "", string mime = "image/*" );
NativeGallery.Permission NativeGallery.GetVideosFromGallery( MediaPickMultipleCallback callback, string title = "", string mime = "video/*" );

// Picking audio files is supported on Android only
NativeGallery.Permission NativeGallery.GetAudioFromGallery( MediaPickCallback callback, string title = "", string mime = "audio/*" );
NativeGallery.Permission NativeGallery.GetAudiosFromGallery( MediaPickMultipleCallback callback, string title = "", string mime = "audio/*" );

// Allows you to pick images/videos/audios at the same time
// mediaTypes: bitwise OR'ed media types to pick from (e.g. to pick an image or video, use 'MediaType.Image | MediaType.Video')
NativeGallery.Permission NativeGallery.GetMixedMediaFromGallery( MediaPickCallback callback, MediaType mediaTypes, string title = "" );
NativeGallery.Permission NativeGallery.GetMixedMediasFromGallery( MediaPickMultipleCallback callback, MediaType mediaTypes, string title = "" );


// Returns true if selecting multiple images/videos from Gallery/Photos is possible on this device (only available on Android 18 and later and iOS 14 and later)
bool NativeGallery.CanSelectMultipleFilesFromGallery();

// Returns true if GetMixedMediaFromGallery/GetMixedMediasFromGallery functions are supported (available on Android 19 and later and all iOS versions)
bool NativeGallery.CanSelectMultipleMediaTypesFromGallery();

// Returns true if the user is currently picking media from Gallery/Photos. In that case, another GetImageFromGallery, GetVideoFromGallery or GetAudioFromGallery request will simply be ignored
bool NativeGallery.IsMediaPickerBusy();


//// Runtime Permissions ////

// Interacting with Gallery/Photos is only possible when permission state is Permission.Granted. Most of the functions request permission internally (and return the result) but you can also check/request the permissions manually
NativeGallery.Permission NativeGallery.CheckPermission( PermissionType permissionType );
NativeGallery.Permission NativeGallery.RequestPermission( PermissionType permissionType );

// If the permission state is Permission.Denied, the user must grant the necessary permission (Storage on Android and Photos on iOS) manually from the Settings. These functions help you open the Settings directly from within the app
void NativeGallery.OpenSettings();
bool NativeGallery.CanOpenSettings();


//// Utility Functions ////

// Creates a Texture2D from the specified image file in correct orientation and returns it. Returns null, if something goes wrong
// maxSize: determines the maximum size of the returned Texture2D in pixels. Larger textures will be down-scaled. If untouched, its value will be set to SystemInfo.maxTextureSize. It is recommended to set a proper maxSize for better performance
// markTextureNonReadable: marks the generated texture as non-readable for better memory usage. If you plan to modify the texture later (e.g. GetPixels/SetPixels), set its value to false
// generateMipmaps: determines whether texture should have mipmaps or not
// linearColorSpace: determines whether texture should be in linear color space or sRGB color space
Texture2D NativeGallery.LoadImageAtPath( string imagePath, int maxSize = -1, bool markTextureNonReadable = true, bool generateMipmaps = true, bool linearColorSpace = false );

// Creates a Texture2D thumbnail from a video file and returns it. Returns null, if something goes wrong
// maxSize: determines the maximum size of the returned Texture2D in pixels. Larger thumbnails will be down-scaled. If untouched, its value will be set to SystemInfo.maxTextureSize. It is recommended to set a proper maxSize for better performance
// captureTimeInSeconds: determines the frame of the video that the thumbnail is captured from. If untouched, OS will decide this value
// markTextureNonReadable: see LoadImageAtPath
Texture2D NativeGallery.GetVideoThumbnail( string videoPath, int maxSize = -1, double captureTimeInSeconds = -1.0, bool markTextureNonReadable = true );

// Returns an ImageProperties instance that holds the width, height and mime type information of an image file without creating a Texture2D object. Mime type will be null, if it can't be determined
NativeGallery.ImageProperties NativeGallery.GetImageProperties( string imagePath );

// Returns a VideoProperties instance that holds the width, height, duration (in milliseconds) and rotation information of a video file. To play a video in correct orientation, you should rotate it by rotation degrees clockwise. For a 90-degree or 270-degree rotated video, values of width and height should be swapped to get the display size of the video
NativeGallery.VideoProperties NativeGallery.GetVideoProperties( string videoPath );

// Returns the media type of the file at the specified path: Image, Video, Audio or neither of these (if media type can't be determined)
NativeGallery.MediaType NativeGallery.GetMediaTypeOfFile( string path );
Android.meta: The metadata for the android native camera in the folder. 
Editor.meta: The medata for the editor in the app. 
NativeGallery.Runtime.asmdef: Native gallery runtime file.
NativeGallery.Runtime.asmdef.meta: The metadata file for the native runtime file. 
NativeGallery.cs: The cs file for the native gallery installed on the phone and lets the app connect the camera to the app. 
NativeGallery.cs.meta: The metadata file in the folder for the native camera.
iOS.meta: the iOS metadata file in the folder. 
### iOS: The iOS folder in the app for the plugins. 
- iPhoneSpeaker.h, iPhoneSpeaker.h.meta, iPhoneSpeaker.m, iPhoneSpeaker.m.meta, iPhoneSpeaker.cs, iPhoneSpeaker.cs.meta : the iPhone speaker files and metadata in the folder. 
### Scenes: The folder for the scenes in the app. 
- ActivityLog.meta: The metadata for the activity log in the scenes folder. 
- Exercises.meta: The metadata for the exercises in the scenes folder. 
- Help.meta: The metadata for the help in the scenes folder. 
- Home.meta: The metadata for the help in the scenes folder. 
- Onboarding.meta: The metadata for the onboarding in the scenes folder. 
- ParentLock.meta: The metadata for the parent lock in the scenes folder. 
- Recorder.meta: The metadata for the recorder in the scenes folder. 
- Settings.meta: The metadata for the settings in the scenes folder. 
### ActivityLog: the activity log folder. 
- ActivityLog.unity: The unity file extension for the activity log file.
- ActivityLog.unity.meta: The activity log metadata file. 
- AddActivity.cs: The cs file to add activities in the activity log. 
- AddActivity.cs.meta: The metadata file to add more activities in the app. 
### Exercises: 
- ChildTimer.cs: The cs file that handles the timer for the child video. 
- ChildTimer.cs.meta: The metadata file for the child timer cs file.
- ChildVideo.cs: The child video CS file, loads VideoMetadata and updates the proficiency bar fill amount. 
- ChildVideo.cs.meta: The metadata file for the child video cs file. 
- ChildVideo.prefab: The .prefab file for the child video. 
- ChildVideo.prefab.meta: The metadata for the prefab file of the child video. 
- ChildVideoManager.cs: Manages the video of the child. Handles the current word, and gets the next word from the exercise scene. It also adds to the proficiency value of the given VideoMetadata struct. 
- ChildVideoManager.cs.meta: The metadata for the child video manager. 
- ExerciseBar.cs: The file for the progress bar that also emits particles on special events. It reacts to a user input given strength, updates progress bar size and changes scrollbar size. 
- ExerciseBar.cs.meta: The metadata for the exercise bar file. 
- Exercises.unity: The unity file for the exercises in the app. 
- Exercises.unity.meta: The metadata for the exercises in the app. 
- EyeTrackers.meta: The metadata file for the eye trackers in the app. 
- FaceMasks.meta: The metadata file for the facemasks in the app. 
- Mic.cs: This file contains the class for capturing and processing envelopes from the microphone. It starts recording audio buffers, updates mic timings, gets the score of the internal envelope with respect to a model word and calls at the end of each replay. It gets envelope and envelope score and processes the buffer. It is set to the lowest sampling rate and gets a buffer every 0.25 secs, starts mic, and processes buffers. 
- Mic.cs.meta: The metadata file for the mic. 
- ModifiedVideoPlayer.cs: It is the driver code for the mic files in the folder. It has instructions such as give it your best shot, repeat after me, etc. 
- ModifiedVideoPlayer.cs.meta: The metadata file for the modified video player instructions. 
- ModifiedVideoPlayer.prefab: The prefab file for the modified video player instructions. 
- ModifiedVideoPlayer.prefab.meta: The metadata file for the modified video player instructions.
- ProficiencyBar.png: The proficiency bar image in the folder. 
- ProficiencyBar.png.meta: The metadata for the  proficiency bar image in the folder.
- RewardsButton.cs: This has the driver Code for RewardsButton in Exercises Scene.
- RewardsButton.cs.meta: The metadata file for the rewards button file. 
- SITA_Instructions.meta: The metadata file for the instructions. 
- NativeGallery.meta: The metadata in the plugins folder for the native gallery where you can choose previous videos from the gallery. 
### SITA_Instructions: contains the mp3 for the instructions in the app. 
- GiveItYourBestShot.mp3: “Give it your best shot” sound. 
- GiveItYourBestShot.mp3.meta: The metadata in the folder for the sound “give it your best shot”. 
- NowItsYourTurn.mp3: “Now it’s your turn” sound.
- NowItsYourTurn.mp3.meta: The metadata in the folder for the sound “now it’s your turn”. 
- NowYouTryIt.mp3: “Now you try it” sound.
- NowYouTryIt.mp3.meta: The metadata in the folder for the sound “now you try it”. 
- RepeatAfterMe.mp3: “Repeat after me” sound. 
- RepeatAfterMe.mp3.meta: The metadata in the folder for the sound “repeat after me”. 
 ### Help: The help options folder in the app. 
- Help.unity: The onboarding unity file for help. 
- Help.unity.meta: The metadata file for help. 
- HelpSettings.lighting: The help settings file. 
- HelpSettings.lighting.meta: The metadata for the help settings file. 
### Home: The home folder in the app. 
- Home.unity: The onboarding unity file for home. 
- Home.unity.meta: The metadata file for home. 
- HomeManager.cs: The driver code the the UI of the home screen in the app. 
- HomeManager.cs.meta: The metadata file for the UI of the home screen. 
### Onboarding: The onboarding folder in the app. 
- Onboarding.unity: The onboarding unity file for the onboarding. 
- Onboarding.unity.meta: The metadata file for onboarding. 
- OnbaordingManager.cs: The driver code the the UI of the onboarding in the app. 
- Onboarding Manager.vs.meta: The metadata file for the UI of the onboarding screen. 
### ParentLock: The parent lock folder in the app. 
- ParentLock.unity: The parent lock unity file. 
- ParentLock.unity.meta: The metadata file for the parent lock. 
- ParentLock.cs: The main cs file that generates the code randomly and checks for the correct code entered. 
- ParentLock.cs.meta: The metadata file for the parent lock. 
- ParentLockSettings.lighting: The lightning app for the parent lock. 
### Recorder: Has the video recorder files.
- AddVideoWizard.cs: Contains the driver class for Add Video prefab
- AddVideoWizard.cs.meta: The metadata file for the add video wizard.
- ParentVideo.cs: Driver Code attached to each ParentVideo prefab.
- ParentVideo.cs.meta: The metadata file for the parent video file. 
- ParentVideo.prefab: The main parent video driver code prefab file.
- ParentVideo.prefab.meta: The metadata for the files listed above. 
- ParentVideoManager.cs: Manages the parent video file.
- ParentVideoManager.cs.meta:  The metadata file for the parent video manager. 
- Recorder.unity: The recorder unity file.  
- Recorder.unity.meta: The metadata file for the recorder unity file.
- RecorderSettings.lighting: The lightning file for recorder settings. 
- RecorderSettings.lighting.meta: The metadata for the recorder settings lighting file in the folder.
- VideoAdder.cs: The cs file that lets users add more videos to the recorder folder. 
- VideoAdder.cs.meta: The metadata file for the video adder cs file.
- VideoAdder_VideoReplay.prefab: This is the prefab file for the video adder file. 
- VideoAdder_VideoReplay.prefab.meta: The metadata file for the file listed above. 
- VideoReplay.cs: The video replay file that lets the user to replay the videos previously uploaded in the folder. 
- VideoReplay.cs.meta: The metadata file for the video replay file.
### Settings: The home folder in the app. 
- Settings.unity: The settings unity file. 
- Settings.unity.meta: The metadata file for settings of the app. 
- SettingsEditor.cs: The cs file for the settings that lets the user change the settings of the app. This includes settings such as volume, number of repeats of each video, etc. 
- SettingsEditor.cs.meta: The metadata file for the settings file. 
### StreamingAssets: The streaming assets folder. Contains buildinfo and the metadata for that file. 
### TextMeshPro: The texts mesh folder
- Documentation.meta: The metadata file for the documentation
- Examples & Extras.meta: The example and extra metadata file. 
- Fonts.meta: the metadata for the fonts file.
- Resources.meta: the resources metadata file.
- Shaders.meta: the shaders metadata file. 
- Sprites.meta: the sprites metadata file
### XR: contains code necessary for AR portion
- Loaders.meta: the loader metadata file.
- Settings.meta: the settings metadata file.
- XRGeneralSettings.asset: the XR settings asset file.
- XRGeneralSettings.asset.meta: the metadata file for the XR general settings.
### appIcon:
- SITA1024.png: The main SITA logo image.
- SITA1024.png.meta: The metadata for the main SITA logo. 
- ParentLockSettings.lighting.meta: The metadata for the parent lock settings. 
- iOS.meta: The metadata in the plugins folder for the iOS build. 
## Packages: JSON files for native camera gallery and native camera. 
## ProjectSettings: The .asset files for the project settings. 
- AndroidLogcatSettings.asset
- AudioManager.asset
- DeviceSimulatorSettings.asset
- ClusterInputManager.asset
- EditorBuildSettings.asset
- EditorSettings.asset
- GraphicsSettings.asset
- InputManager.asset
- NavMeshAreas.asset
- NetworkManager.asset
- PackageManagerSettings.asset
- Physics2DSettings.asset
- PresetManager.asset
- ProjectSettings.asset
- ProjectVersion.txt
- QualitySettings.asset
- TagManager.asset
- TimeManager.asset
- UnityConnectSettings.asset
- VFXManager.asset
- VersionControlSettings.asset
- XRPackageSettings.asset
- XRSettings.asset

# SetUp 

## End-user installation and setup: 
1. Download the SITA iOS application from the Apple Store.
2. Open the app and go into therapist mode.
3. Input the correct code. 
4. Click the settings icon on the bottom left and personalize settings as desired Default settings are the following:
5. Exercises per reward: 3
6. Max playtime reward: 20
7. Repeats: 10
8. Instruction volume: -20 dB
9. Exercise start volume: -5 dB
10. Target score: 50
11. Playtime theme: Animals 
12. Parent Lock: ON
12. To record the first exercise, click: “Add Exercise”. Read the instructions and hit “Continue”. Enter a name for the exercise and then give SITA permission to access the phone’s microphone and camera.

## Admin (developers)  installation and setup:
1. Download Unity version 2020.1.8f and the iOS extension.
2. Download Xcode.
3. Clone the SITA repository in your local machine and open the project on Unity
4. In build settings select iOS as the platform and “Latest version” in the “Run in Xcode” dropdown. Additionally, select run in Xcode as “Release”.
5. Click on “Build” and select a folder to save the build file to a location on your disk.
6. Upon successful completion of the build on Unity, open the project in Xcode and connect an iPhone to the computer.
7. Select the iphone “Unity-Iphone > Device Name” at the top of the Xcode screen next to the build symbol. 
8. Click on Unity-iPhone in the Project Navigator, and then click on Signing & Capabilities. Under All, check “Automatically manage signing,” as this will handle all of the Signing Certificates and Provisioning Profiles that are necessary to build to the device.
9. Next, log into the Apple Developer account associated with this project and select ImagiRation LLC under the Team dropdown. Once this is complete, unlock your iPhone, build the project using the Play button, and it will run on your device.
10. If desired the app can be internally tested through Testflight:
11. In Xcode, open the project and make sure the target is set to Unity-iPhone.
12. Under Signing & Capabilities, add the Push Notifications capability.
13. Under General, increment the Build number by 1. For example, if the build number is set at 042, change it to 043.
14. In the Product dropdown menu at the top of the screen, click on “Archive”. Xcode will now begin archiving the project; this is a necessary step for uploading the app to TestFlight.
15. Upon successful completion of archiving the app, a dialog box pops up (this can also be accessed by clicking Organizer in the Window drop down). This dialog box gives you the option to both validate and distribute your app.
16. Select “Validate App” and check both distribution options. Click “Automatically Manage Signing” and then “Validate”. 
17. Once the app is successfully validated, it is time to distribute the app. Click on Distribute app. Select App Store Connect, then upload. 	
18. Once the upload is complete, go to appstoreconnect.apple.com and sign in with your developer account. 
19. Under My Apps, select SITA and go to the TestFlight tab. The app will be processing for 24-48 hours; however, once that is complete, click on the appropriate Build (in this case, it is Build 043) and invite testers via email.
20. The testers w
