# FAAproject

This script matches the addresses to records in your database with those in the FAA's public aircraft registry. 

Excerpted from archived blog post:
This post outlines the process I used to match our alumni records who might have a plane. I was inspired to do this after finding that the FAA makes their entire aircraft registry publicly available for download. The problem is that their registry is over 300,000 records. 

To start, you’ll need to download and install the R programming language on your computer (available here: https://cran.r-project.org/). 

Then, you’ll do the same for the integrated development environment (IDE for short, just an easier way to use R) on your computer (you want the desktop version, available here: https://www.rstudio.com/products/rstudio2/).

Once installed, you can open RStudio (the IDE) and open “PlaneProjectExternal.R” (see the .R file at https://github.com/rwestdfci/FAAproject). 

For the FAA data: Use the link in line 13 of the code to navigate to the FAA website, scroll to the bottom and click “Download the Aircraft Registration Database.” This will download a zipped file. You want to unzip it and drag the file called “MASTER.txt” to your desktop. 

For your constituent data: Export whoever you want to check out of your CRM (I did all people we had home addresses for just to be thorough). Open the file in Excel and do the following:
Save it as a .csv called “YOURCONSTITUENTBASE” (Excel should append “.csv” but be sure to doublecheck that) to your desktop
Make sure you only have the four columns we need (ID number, home street address, home city, home state)
Rename the columns as follows “Entity.ID”, “Home.Address.Line.1”, “Home.City”, “Home.State” (without quotes)
Save and close it.

In RStudio:
In line 2, you need to enter the path to your desktop and it will vary based on your OS. If you’re on Windows, you can just drop your username into the existing path.
To execute lines in R, you just click into a line (no need to select anything) and hit ctrl+enter
Starting at line 2, execute each line, working all the way to line 45 in order. Feel free to skip lines starting with # (those are just explanations). 

Once line 45 has been executed, you should have a .csv on your desktop (“PotentialPlanes.csv”) which will contain all IDs who had a home address that matched an address in the FAA registry. Proceed and prioritize as you like!

A note on executing lines in R: Some lines take a while to execute depending on what it is (reading the FAA file takes about a minute on my newish laptop); you’ll know the code is still processing because when you look in the console frame (bottom left of RStudio), there will be a stop sign in its header. It’s best not to execute the next line until that has stopped in case there is an error. If you encounter an error, let me know which line of code triggered it and we will fix it!
