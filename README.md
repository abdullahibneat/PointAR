# PointAR
PointAR is a concept app showcasing the use of Augmented Reality to assist the foreign workforce with the induction process through the use of 3D animation for visualisation and built-in translations.

![In-app screenshot](https://i.imgur.com/i0LAJia.jpg)

## Markers
The app was developed with the following 2 signs in mind:

!["Lift with your legs" sign](https://i.imgur.com/sG6ULEg.png)!["Open holes" sign](https://i.imgur.com/vGdgmPg.jpg)


## Scripts
The app has the following three custom scripts, coded in C#, within the "/assets/[_Scripts](https://github.com/abdullahibneat/PointAR/tree/master/Assets/_Scripts)" folder:

| Name                 | Description                                                                  |
|----------------------|------------------------------------------------------------------------------|
| AutoFocus.cs         | *Used to configure Vuforia to use autofocus on the device's camera.*         |
| playbackspeed.cs     | *Controls the playback speed of the animation.*                              |
| translate.cs         | *Used to translate each sign by selecting a language from a drop-down menu.* |

Each script includes in-line comments explaining what the line is used for.

## How to use
1. Begin by downloading the project and opening it into Unity. Note the project was last used in `Unity 2018.1.6f1`.
2. Navigate to the `_Scenes` folder, and load the `main` scene by double-clicking it.
3. Select the `AR Camera` component from the hierarchy, and under the `Vuforia Behaviour` component, click on `Open Vuforia Configuration`.
4. Press the `Add license` button just below the App License Key field. This step is required for Vuforia to be enabled. You will be redirected to the [Vuforia Dev Portal](https://developer.vuforia.com/license-manager). Login or register with a free account, and generate a new license key.
5. Copy the license key and paste it into the `App License Key` input field encountered in step 3.

## How it works
The main menu consists of a `drop-down menu` and a `start button`. The scene is composed of two Vuforia `ImageTarget` GameObjects, one for each sign, with images of the translated sign as children GameObjects.
The drop-down menu has the script `translate.cs` attached as a component, and takes each translated sign as an input.

![Overview of translate.cs component](https://i.imgur.com/ytv4URZ.jpg)

The script then creates an event, `onValueChange`, which detects when the user changes the language. Each sign is hidden by default. When the `onValueChange` event is triggered, it will display the correlated sign (i.e. "Italian" will un-hide the Italian translation, while keeping "Lithuanian" and "Urdu" translations hidden).

## Export for Android
Make sure you have the [required software](https://docs.unity3d.com/Manual/android-sdksetup.html) installed beforehand. Open the `Build settings` dialogue from the `File` menu, and press `Build`.

## Export for iOS
Follow Unity's [Getting started with iOS](https://docs.unity3d.com/Manual/iphone-GettingStarted.html) guide.