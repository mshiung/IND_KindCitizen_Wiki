# Setup project info

status of remaining test cases

https://docs.google.com/spreadsheets/d/1ZIOQRwf9Fw7FSBUHjXzIDGZ5-shGDH7LZii1enh_kY8/edit?usp=sharing

## Project Setup


**1. Install your C# IDE (I used Visual Studio Community 2019)**

**2. Git clone KindCitizen_UITests** 

Click on Git
![image.png](/.attachments/image-39beb724-f96e-4c05-a029-f33b26ee333e.png)

Click on Clone Repository

![image.png](/.attachments/image-8dc920c7-5356-4408-a4c6-0c0e9df5c3da.png)

Paste https://NanyangPoly@dev.azure.com/NanyangPoly/IND_KindCitizen/_git/IND_KindCitizen_Tests
into url to clone, login with your outlook account if prompted.

**3.NuGet Necessary Packages**

Now use NuGet Package Manager (Project > Manage Nuget Packages) to install these packages 
![image.png](/.attachments/image-3820f74b-dffa-47d4-80dc-f9eb6f089d71.png)


##Testing

These tests are written in C# in a framework called Selenium. 
Selenium is basically a tool to automate browsers.
In this case, we are using Selenium to run preprogrammed steps on the KindCitizen Website in order to test the functions of the website.

You may view the code or resources online to get an idea of how the tests work. 

You can view all your completed tests in the Test Explorer (Test > Test Explorer). This will be how you run all the tests that you will be writing. 

![image.png](/.attachments/image-5f1943aa-49d6-4c1f-a170-aab6f30c49e9.png)








**Possible Enhancement**


Optimize tests

Make certain tests work on Azure Pipelines



Possible Changes