# IOS Shortcut Code to generate a TOTP

Creating primarily for a reminder to myself. May help somebody else out.

I had a usecase where I was wanting to connect to openVPN with a TOTP & Password & Key from an iPhone. 6 digit totp generation can be done many ways generally via an AUTH app. I was in search of having it automatically loaded into the IOS clipboard via IOS shortcuts. Then when openVPN prompted, paste and connect. I couldn't find anything on the web so took a different approach.

That led me to find [otpauth](https://github.com/hectorm/otpauth). The javascript contained therein can be run directly from a webbrowser and doesn't have remote dependancies if you copy the code to a local file.

## IOS Shortcut

![Shortcut][IOS_Shortcut]

Manual Fix
![JS][JS]

Dict CallOut
![Dict][Dict]

[IOS_Shortcut]: images/IOS_Shortcut.jpeg
[JS]: images/JS_Manual_Fix.jpeg
[Dict]: images/DictionaryKey.jpeg

## IOS Shortcut Notes
1. Recieve Input is used for deciding if we send to clipboard or just show alert with value.
2. Dictionary is what TOTP params are.
3. Text field is from [here](https://github.com/njobrien1006/otpauth_ios_shortcut/blob/main/JavaScript). Which is modified version of [otpauth](https://otpauth.molinero.dev/). The [JS](https://cdn.jsdelivr.net/npm/otpauth/dist/otpauth.esm.min.js) portion.
4. Replace is needed for new lines as it doesn't aggree for some reason.
5. URL Form puts together and URL encodes the text.
6. URL decode effectivly runs the baked in javascript.
7. Then we decide if it goes to clipboard or an alert is displayed.
