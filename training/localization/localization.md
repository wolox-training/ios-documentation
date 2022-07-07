## String Localizable Tutorial

#### What is a localizable.string file? 

It’s a file where you add translation data as key-value pairs. That means that you set a name for every string that you are going to use on the code, and you use that name instead of the actual string. it looks something like this:  
 
#### Why should I use it? 

The main advantage of using it, is that it makes it very easy to add new languages to your app. You just have to create a new localizable file for your new language with the same keys as the original file, and you change the values with the translated versions of the strings. It’s very important to do this from the start of your project, even when you are not sure if you are going to release your app in other languages it is recommendable to do it anyways, since it takes almost no effort to do it, but trying to translate an app that doesn’t have it’s strings localized can take forever. 

Apart from that, localizing your strings is a nice and organized way of having all your texts in one place, it makes it easy to avoid using duplicate texts. 
 
#### Okay, you convinced me. How do I start?

Recent versions of XCode doesn’t create Localizable.strings file by default.  
To add Localizable.strings file, go to File -> New -> File, choose Strings File under Resource tab of iOS, name it Localizable.strings, and create the file. 

Now, you have a Localizable.strings file for your base language as below. 

Let’s add words and phrases used in the app to the Localizable.strings file of the project. 


Now we are ready to use our texts in the app, so how should you use them?

Swift provides us with the NSLocalizedString method.

Let’s say I want to use the “welcome” string on a label, I would have to do something like this: 

That looks a little ugly, luckily for you, if you are using wolmo core you can just do this instead: 

Way better, right? 

Now let's say that we want to add the name of the user to the welcome label, we would need to modify the string localizable: 


This way the string knows that it will receive another string as a parameter. 
To use this text now we have to use the localized() function like this: 

#### Awesome! And what about another language? 

Now that you have your Localizable.strings file, adding a new language is simple. 
Open your Localizable.strings file, and in the file inspection (right panel) select spanish. If you do not have this option, open your project settings, and under PROJECT add spanish in Localizations

Now you get one Localizable.strings file for each language, something like this: 

All you need to do now is to open your spanish file and change all the value strings with the text you want to show when using spanish language. 
 
#### Finally... My App's name 
 
The app itself can have a different name depending on the user’s language. The name that is displayed on the iPhone’s home screen comes from the Bundle name setting in Info.plist or if present, the Bundle display name setting. 
To localize the strings from Info.plist, you need a file named InfoPlist.strings. 
- Add a new Strings File to your project, and name it InfoPlist.strings.
- Open InfoPlist.strings and press the Localize... button from the File inspector. Choose the English localization; also add a Spanish localization for this file. 
- Open the spanish version and add: CFBundleDisplayName = "Your spanish app name";

With this, the name of your app changes with the device language.[Salto de ajuste de texto]If you need to change any setting from the Info.plist, you just need to add the key in this file with the message you want to show, e.g. the description you set for camera usage. 