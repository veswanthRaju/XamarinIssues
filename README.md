# XamarinIssues
> Issues faced while creating an app in Xamarin

1. Xamarin.Auth Facebook Login error: 
	
    *You are not logged in. Please Login and try again.*
    
 ###### Solution:-
 Go to the settings section of your app in Facebook (Facebook developers > My Apps then Settings)
Under the Basics make sure you have the respective platform. If you do and it is still not working, then remove and recreate it. Otherwise, click on [+ Add Platform] and follow the instructions. For example, for Android you need to provide: a) Your package id b) Your launcher activity full name c) Key hash - which you need to generate as per instructions using keytool and openssl.
The solution screenshot is like this:



Change Redirect Uri it should  match with   
```csharp
(var auth = new OAuth2Authenticator(
                clientId: "332063047134905",
                scope: "public_profile",
                authorizeUrl: new Uri("https://m.facebook.com/dialog/oauth/"),
                redirectUrl: new Uri("http://www.facebook.com/connect/login_success.html")));
```
