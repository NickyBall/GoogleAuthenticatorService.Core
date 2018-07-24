# GoogleAuthenticatorService.Core

### Description
This library was rebuilt of https://github.com/BrandonPotter/GoogleAuthenticator, which is built for .NET Framework. This library is meant to setup and use two-factor authentication with Google Authenticator for .NET Core 2.0

### Installation
Via Nuget
```
Install-Package GoogleAuthenticatorService.Core
```

### Getting started
1. Generate Setup Code.
```
TwoFactorAuthenticator Authenticator = new TwoFactorAuthenticator();
var SetupResult = Authenticator.GenerateSetupCode("<Title>", "<Secret Key>", 250, 250);
string QrCodeUrl = SetupResult.QrCodeSetupImageUrl,
string ManualCode = SetupResult.ManualEntryKey
```

2. You'll get something like this.
[Imgur](https://i.imgur.com/Klhgvn2.png)

3. Setup Code to your Google Authenticator App.

4. When using, you can verify code like this.
```
TwoFactorAuthenticator Authenticator = new TwoFactorAuthenticator();
bool ValidateResult = Authenticator.ValidateTwoFactorPIN("<Secret Key>", "123456");
```
