# CICD_tutorial
Repository to perform the actions along with the following video: https://www.youtube.com/watch?v=SOtC1VLZKm4

The following changes in the process are necessary to make sure you can follow along:


# dotnet
GET is different location; the sample project now contains "WeatherForecastController" instead of "ValuesController". Go to https://localhost:5001/weatherforecast to see the results
Simplest way forward are some small changes to this controller to make it work with the rest of the tutorial. Go ahead and fork my version to keep going. See here: https://github.com/Thomasvdw/CICD_tutorial

# YAML:
the .yml file coming from Azure has a different syntax, includes testing immediately. But if this testing fails it does not stop the build for some reason. 
"DotNetCoreCLI@2" results in warning as version 2 is deprecated. For now still seems to work though. 

# Release pipeline: 
With default settings I received the following error on release atttempt: "##[error]Error: More than one package matched with specified pattern: D:\a\r1\a\**\*.zip. Please restrain the search pattern." To fix this; go inside the Edit the release pipeline job, select the "Deploy Azure Service App" and scroll down to "Package or folder". Here don't make it search for any zip (*) but just select the single instance; "..../drop/SimpleAPI.zip". 

