# Guelph Active Transportation Snow Removal Requests

## Purpose
For habitual trips during the winter I often see the same places with inadequate snow removal.
The service request form is geared towards not just one road, but one particular place with snow in it.
It can be a hindrance to either use a form for many different locations or to fill out many forms to submit requests.
This is a quick and dirty solution to automate filling out the forms.

## Overview
I have created a set of convenience Autofill Scripts for filling out forms for various non-motorized modes of travel.  Note that these **WILL NOT** submit the forms, only fill them out.  You will need to click the Submit button to submit the request.
* Bike Lanes
  These can be found here: https://github.com/ccastillo232/guelph-at-snow-removal-requests/tree/main/bike_lanes

* Sidewalks

  These can be found here: https://github.com/ccastillo232/guelph-at-snow-removal-requests/tree/main/bus_stops

* Bus stops

  These can be found here: https://github.com/ccastillo232/guelph-at-snow-removal-requests/tree/main/sidewalks


## Requirements
To use this you will need the Selenium IDE plugin for the chromium browsers.
I have only tested this on Chrome on a Windows 10.  As far as I know it Selenium is not supported on mobile.



## How to Use

This example uses bike lanes, but similar steps can be used for sidewalks and bus stops.

### Install Selenium IDE:

1. Open Chrome and navigate to https://chrome.google.com/webstore/detail/selenium-ide/mooikfkahbdckldjjndioackbalphokd 

   ![SeleniumIDEHomePage](assets\images\SeleniumIDEHomePage_clickAddToChrome.png)

2. Click Add to Chrome.  Review the permissions and accept to Add the extension to your browser.

3. Click the extensions button in Chrome and pin the Selenium IDE icon to make it visible. 

   <img src="assets\images\PinSeleniumIDE.png" alt="PinSeleniumIDE" style="zoom:50%;" />

4. You should now have the Selenium IDE extension installed and readily available from Chrome. 

   <img src="assets\images\SeleniumIDEInstalledAndAvailable.png" alt="SeleniumIDE_InstalledAndAvailable" style="zoom:50%;" />



### Download the Autofill Script

1. Navigate to https://github.com/ccastillo232/guelph-at-snow-removal-requests/tree/main/bike_lanes 

   <img src="assets\images\GitHub_BikeLane_Homepage.png" alt="GitHub_BikeLane_Homepage" style="zoom:50%;" />

2. Decide which Autofill Script you need.  E.g. if your typical trip contains 2 streets with bike lanes that need clearing, select *clear_2_bike_lanes_request.side*.

3. Download the Autofill Script by clicking the file name.  This takes you to the file preview page. 

   <img src="assets\images\GitHub_BikeLane_FilePreview_RawButton.png" alt="GitHub_BikeLane_FilePreview" style="zoom:50%;" />

4. Right click the Raw button and select *Save link as...*  and save it to a known location. 

   <img src="assets\images\GitHub_BikeLane_FilePreview_RawButton_SaveAs.png" alt="GitHub_BikeLane_FilePreview_RawButton_SaveAs" style="zoom:50%;" />

## Modify the Autofill Script

1. In Chrome, navigate to the snow removal request form.  You will want to use this as a reference as you modify the Autofill Script for yourself. https://forms.guelph.ca/Operations/Snow-removal-roads  

   <img src="assets\images\GuelphSnowRemovalRequstForm.png" alt="GuelphSnowRemovalRequstForm" style="zoom:50%;" />

2. In Chrome, click the Selenium IDE extension button to open Selenium IDE.  Choose *Open an existing project*.  Select the Autofill Script you previously saved.  

   <img src="assets\images\SeleniumIDE_OpenProject.png" alt="SeleniumIDE_OpenProject" style="zoom:50%;" />

2. You will now see the Selenium IDE with the script loaded.  I have broken the script into sections.  At the top is the first section, Form Field Values.  This is where you will need to make your changes.

3. First edit section 1a, Common Field Values.  This is your personal/contact information, and will be used for each snow removal request you make.  **Do not modify the *Description of the problem* field.**<img src="assets\images\BikeLane2_1a_CommonFields.png" alt="BikeLane2_1a_CommonFields" style="zoom:50%;" />

   Each line in the script will store the Target value so that it can be entered in the snow request form.  You will need to change the values by selecting each line and changing the Target value.  For example in the next screenshot I have changed the First name from *Max* to *Betty*. <img src="assets\images\BikeLane2_1a_EditFirstName.png" alt="BikeLane2_1a_EditFirstName" style="zoom:50%;" />

   Each step corresponds to a field in Guelph's Snow Removal Request Form.  If you leave a Target blank then it will be blank on the form.  One exception is *May we contact you* - this is required and must be **Yes** or **No**.

4.  Next edit section 1b, Trip Info.  Depending on which script you downloaded you will see 1-5 legs (roads) in this section.  In this case we see 2 legs.

   <img src="assets\images\BikeLane2_1b_TripInfo.png" alt="BikeLane2_1b_TripInfo" style="zoom:50%;" />

5. Edit the fields with your streets.  Note that each street name must match exactly the street names in the form request.  To make sure you've typed the street name correctly go to the form in your browser and find the Street name field.  Enter the street name.  In the dropdown list you should only see one matching entry.

   <img src="assets\images\BikeLane2_1b_StreetNameMatching.png" alt="BikeLane2_1b_StreetNameMatching" style="zoom:50%;" />

6. Save the changes by clicking the save button.  It is a good idea to give it a new name that is meaningful to you.

   <img src="assets\images\BikeLane2_Save.png" alt="BikeLane2_Save" style="zoom:50%;" />

7. Run the script.  Note that the script **WILL NOT** submit the form, only fill it out.

   <img src="assets\images\BikeLane_RunButton.png" alt="BikeLane_RunButton" style="zoom:50%;" />

   A new Chrome browser should open, navigate to the request form, and autofill with your values.  If your script has more than 1 leg, a new tab will open for each leg.  For example the below screenshot has 2 tabs for 2 legs.

   <img src="assets\images\BikeLane_ScriptResults.png" alt="BikeLane_ScriptResults" style="zoom:50%;" />

8. If everything looks good then you've got the script you need.  Now whenever your bike lanes are not cleared you can run the script then click the Submit buttons to submit your requests.