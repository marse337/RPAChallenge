Here is a README.md file with details on using OpenRPA and Google Sheets to complete the RPA challenge:

For a video demonstration please watch [This](https://youtu.be/JhaDkPKDa9c)

# Completing the RPA Challenge with OpenRPA and Google Sheets

## Overview

This project uses OpenRPA and Google Sheets to automate filling out the form on the [RPA Challenge](https://rpachallenge.com/) website. Please visit [OpenRPA Github](https://github.com/open-rpa/openrpa) for more information

### Tools Used

- [OpenRPA](https://github.com/open-rpa/openrpa/releases/latest/download/OpenRPA.msi) - open source RPA tool
- Google Sheets - for generating test data
- [RPA Challenge website](https://rpachallenge.com/) 

## Before Starting - Setup

1. Import the OpenRPA flow
2. Generate test data in Google Sheets
   - Columns for first name, last name, company, role, address, email, phone
   ## Steps Once Setup is complete
Press Start in OpenRPA 
OpenRpa will
   - Extract each column of data from Sheets and convert to a CSV string
   - Navigate to the RPA Challenge site
   - Insert a JavaScript snippet into the console to fill out the form
   - Update the google sheet when complete

## Code

The OpenRPA flow extracts each column from Sheets and converts it into a CSV string:

```csharp
string text = @PhoneNumber; 

// Split the string by newline
string[] lines = text.Split(new[] { "\r\n", "\n", "\r" }, StringSplitOptions.RemoveEmptyEntries);

// Skip the first row and surround each line with single quotes 
// and join them with commas
PhoneNumber = string.Join(", ", Array.ConvertAll(lines.Skip(1).ToArray(), line => "'" + line + "'"));
```

The JavaScript snippet to populate the form:

```js
document.querySelector('.waves-effect.col.s12.m12.l12.btn-large.uiColorButton').click();

const firstName=[FirstName]; 
// ...

for(let i=0;i<firstName.length;i++) {

  document.querySelector('[ng-reflect-name=labelFirstName]').value=firstName[i];
  
  // ...
  
  document.querySelector('.btn.uiColorButton').click();
}
```

## Results

- Automated form submission on the RPA Challenge site using realistic test data
- Demonstrated RPA automation with OpenRPA and Google Sheets

