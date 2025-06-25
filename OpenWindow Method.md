# OpenWindow method
11/25/2024
Opens a new browser window which navigates to the specified URL. The benefit of using this function instead of using the native browser function, is that this function also works when using the control add-in in an app, for example on a phone. If you are using the native browser function in an app, the behavior varies between the different platforms (Windows, iOS, Android).

# Method signature
void Microsoft.Dynamics.NAV.OpenWindow(url)

# Parameters
Parameter	Description
url	Type: String

A string that contains the URL for the new browser window to navigate to.
# Related information
AL method reference
GetEnvironment method
GetImageResource method
InvokeExtensibilityMethod method
Asynchronous considerations