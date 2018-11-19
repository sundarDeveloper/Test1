# Environment
Miscrosoft Visual Studio Community 2017 Edition

# Source code (7Z archive) is avaliable in the following google drive
https://drive.google.com/drive/folders/1OebN-MsPHKLExSjS66rTZIDVJqs1Fmx0?usp=sharing

# Projects:
- RoadStatus 
    * Console Application - .Net Core
  
    * bThis app will connects to REST API at https://api.tfl.gov.uk and get status of major roads and display the results in console.
   
- RoadStatus.Tests
   * Mstest project
   * It is a test application written in Mstest and data mocking done using Moq 4.10.0 

# Build and Test steps.
- Download the application from the google drive and extract to local machine (for example c:\TFLTest
- open the solution file "RoadStatus.sln" using Visual Studio
- Build the solution
- From visual studio solution explorer select RoadStatus project and Select Publish option to publish console app. 
- Publish Target Location is set to "bin\Release\netcoreapp2.1\publish"
- once publish completed, open the appsetting.json file from applications folder "RoadStatus\RoadStatus\bin\Release\netcoreapp2.1\win-x64"
- updated the user credential details for accessing the Rest API https://api.tfl.gov.uk. Enter your API_ID and APP_Key values that you got when registering in https://api-portal.tfl.gov.uk/ and save and close the file.
-  Following is the appsettings.json format
        {

          "BaseAddress": "https://api.tfl.gov.uk/",
          "AppId": "userAppID",
          "AppKey": "userAppKey"
        }
 - Application can be execute from Windows Powershell window.
    In the powershell window go the following folder "RoadStatus\RoadStatus\bin\Release\netcoreapp2.1\win-x64"
* PS C:\TFLTest\RoadStatus\bin\Release\netcoreapp2.1\win-x64> .\RoadStatus.exe A23
    The status of the A2 is as follows
        Road Status is Good
        Road Status Description is No Exceptional Delays
        
 * PS C:\TFLTest\RoadStatus\bin\Release\netcoreapp2.1\win-x64> echo $lastexitcode
 0

* PS C:\TFLTest\RoadStatus\bin\Release\netcoreapp2.1\win-x64> .\RoadStatus.exe A233
A233 is not a valid road

 * PS C:\TFLTest\RoadStatus\bin\Release\netcoreapp2.1\win-x64> echo $lastexitcode
 1
 
 
 - Test steps
 * Test can be run from power shell command prompt for from inside visual studio
    * Running test from command prompt
    * open powershell windon and go to folder C:\TFLTest\RoadStatus\RoadStatusTest
    * run the following command from command prompt
    * PS C:\TFLTest\RoadStatus\RoadStatusTest> dotnet test
    * Test will run and you will get the test result on the console.

    
