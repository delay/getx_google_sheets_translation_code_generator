
## GetX Google Sheets Translation Code Generator

When handling localization for my app I was using the excellent [https://pub.dev/packages/flutter_sheet_localization](https://pub.dev/packages/flutter_sheet_localization) package. I have also been using the GetX package. GetX now has their own translation code options so I wanted the benefits of storing my translations in google sheets but also wanted the ability to have the code I would need for GetX generated automatically since you must write a lot of tedious code to translate your app.

I created a code generator that will do this.

So let me explain how it works. You need to create a translation for your app in google sheets.

![](https://cdn-images-1.medium.com/max/2000/0*np0ZcUgEyUHVBTv1)

You can copy my [sheet](https://docs.google.com/spreadsheets/d/1oS7iJ6ocrZBA53SxRfKF0CG9HAaXeKtzvsTBhgG4Zzk/edit#gid=0) as a starting point for your own app. The cool thing about using a google sheet is you can have google translate a field with a simple google formula: =GOOGLETRANSLATE(B4,en,fr) This says translate the phrase in field B4 from english to french. Next you can edit the main.dart file in the [project](https://github.com/delay/getx_google_sheets_translation_code_generator) I listed earlier and edit these two lines.

    //the document id for your google sheet  
    String documentId = "1oS7iJ6ocrZBA53SxRfKF0CG9HAaXeKtzvsTBhgG4Zzk";  //the sheet id of your google sheet  
    String sheetId = "0";

The next step is to go to the command line and change to the lib/ directory. Then type:

    dart main.dart

This will create a localization.g.dart file with your generated code that looks like this.

![](https://cdn-images-1.medium.com/max/3264/1*OXPz9LP3ngV2dqKe_CGe1A.png)

You can then use these translations in your own project with something like this.

    Text('settings.updateProfile'.tr)

You can find out more about how to use getX translations [here](https://pub.dev/packages/get#internationalization).

Anyway I hope you will find this useful for your own projects. If you would like to see how I used this in a project you can take a look at my [getX flutter starter project](https://jeffmcmorris.medium.com/getx-flutter-firebase-auth-example-b383c1dd1de2)

