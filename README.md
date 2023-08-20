# RPAChallenge
Using OpenRPA and Google sheets to complete a challenge

Requirements- 
OpenRPA - Import the flow
Use Google Chrome- Google Sheets- Create dummy data 
Use Google Chrome- Visit https://rpachallenge.com/

Walking through the steps
Navaigate to each column in Google sheets, Save each column as a variable
convert each variable as a single line and have each item separated out by commas and single quotes Here is my c# code

string text = @PhoneNumber;
// Split the string by newline
string[] lines = text.Split(new[] { "\r\n", "\n", "\r" }, StringSplitOptions.RemoveEmptyEntries);
// Skip the first row and surround each subsequent line with single quotes and join them with commas
PhoneNumber = string.Join(", ", Array.ConvertAll(lines.Skip(1).ToArray(), line => "'" + line + "'"));

text = @EmailVar;
// Split the string by newline
lines = text.Split(new[] { "\r\n", "\n", "\r" }, StringSplitOptions.RemoveEmptyEntries);
// Skip the first row and surround each subsequent line with single quotes and join them with commas
EmailVar = string.Join(", ", Array.ConvertAll(lines.Skip(1).ToArray(), line => "'" + line + "'"));

text = @AddressVar;
// Split the string by newline
lines = text.Split(new[] { "\r\n", "\n", "\r" }, StringSplitOptions.RemoveEmptyEntries);
// Skip the first row and surround each subsequent line with single quotes and join them with commas
AddressVar = string.Join(", ", Array.ConvertAll(lines.Skip(1).ToArray(), line => "'" + line + "'"));
       
text = @CompanyName;
// Split the string by newline
lines = text.Split(new[] { "\r\n", "\n", "\r" }, StringSplitOptions.RemoveEmptyEntries);
// Skip the first row and surround each subsequent line with single quotes and join them with commas
CompanyName = string.Join(", ", Array.ConvertAll(lines.Skip(1).ToArray(), line => "'" + line + "'"));
       
text = @LastName;
// Split the string by newline
lines = text.Split(new[] { "\r\n", "\n", "\r" }, StringSplitOptions.RemoveEmptyEntries);
// Skip the first row and surround each subsequent line with single quotes and join them with commas
LastName = string.Join(", ", Array.ConvertAll(lines.Skip(1).ToArray(), line => "'" + line + "'"));
       
text = @FirstName;
// Split the string by newline
lines = text.Split(new[] { "\r\n", "\n", "\r" }, StringSplitOptions.RemoveEmptyEntries);
// Skip the first row and surround each subsequent line with single quotes and join them with commas
FirstName = string.Join(", ", Array.ConvertAll(lines.Skip(1).ToArray(), line => "'" + line + "'"));
      
text = @RoleInCompany;
// Split the string by newline
lines = text.Split(new[] { "\r\n", "\n", "\r" }, StringSplitOptions.RemoveEmptyEntries);
// Skip the first row and surround each subsequent line with single quotes and join them with commas
RoleInCompany = string.Join(", ", Array.ConvertAll(lines.Skip(1).ToArray(), line => "'" + line + "'"));


This is the script that I insert into my clipboard
"document.querySelector('.waves-effect.col.s12.m12.l12.btn-large.uiColorButton').click();const firstName=["+FirstName+"];const lastName=["+LastName+"];const companyName=["+CompanyName+"];const roleInCompany=["+RoleInCompany+"];const address=["+AddressVar+"];const email=["+EmailVar+"];const phoneNumber=["+PhoneNumber+"];for(let i=0;i<firstName.length;i++){document.querySelector('[ng-reflect-name=labelFirstName]').value=firstName[i];document.querySelector('[ng-reflect-name=labelLastName]').value=lastName[i];document.querySelector('[ng-reflect-name=labelCompanyName]').value=companyName[i];document.querySelector('[ng-reflect-name=labelRole]').value=roleInCompany[i];document.querySelector('[ng-reflect-name=labelAddress]').value=address[i];document.querySelector('[ng-reflect-name=labelEmail]').value=email[i];document.querySelector('[ng-reflect-name=labelPhone]').value=phoneNumber[i];document.querySelector('.btn.uiColorButton').click();}"
Go to the window for RPA challenge, Open Console, paste the clipboard
Navigate to Google sheets to update it is complete
