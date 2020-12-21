# IBAN-Manager-Library 
Library to generate check digits for artificial IBANs and check validity of IBAN codes.


Dependencies:

1. System.Numerics 
2. System.Collections.Concurrent
3. .NET Framework 4.6.1
4. .NET Standard 2


Installation:
1. From the nupkg file in this repo
2. From NuGet Gallery (https://www.nuget.org/packages/IBANManager/)
3. From the NuGet Package Manager in VS by browsing the NuGet Gallery directly
4. From the .dll file in this repo, needs to be added as a reference

The IBAN table will be loaded from table.ini which needs to be placed next to the app executable, also needs to be distributed with the final app.
table.ini can be found here: https://github.com/adrenaline96/IBAN-Manager-Library/blob/master/table.ini


Usage examples: https://pastebin.com/ymtuRTfH


using IBAN_Manager;
 
            //table.ini can be had here https://github.com/adrenaline96/IBAN-Manager-Library/blob/master/table.ini
            IBANManager ibm = new IBANManager("RO00AAAA1B31007593840000");  //object with artificial IBAN (00 check digits)
 
            string ibanWithCheckDigits = ibm.GenerateValidIban(); //the valid IBAN with valid check digits will be generated
 
            IBANManager ibm2 = new IBANManager("RO49AAAA1B31007593840000"); 
 
            string ibanStatus = ibm2.CheckIban();  //checks if the IBAN is valid, ibanStatus will be "Invalid" or "OK"
 
            string ibanCode = ibm2.GetIban(); //returns IBAN code from the object
