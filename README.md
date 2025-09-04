# Bug-Bounty-History 2025

# July
1) Pmiz (Bugv) (3-4 weeks)  
   A) Profile and Password Update Allowed Without Email Verification - `High`
   - Result : Not Applicable (they already know)
    - Improper Access Control/Authorization
    - Summary : App allows user to update their profile details(passwd etc.) without taking the ownership of the email(with unverified email)
                Because app was providing the auth token without verifying the email. 
    - Ref - https://mokhansec.medium.com/bypassing-2fa-in-a-public-bug-bounty-program-a-6000-journey-bae8a5418461

  B) OTP Verification Endpoint Missing Rate Limiting - `High` 
   - Result : Not Applicable (they already know)
    - Improper Authentication
    - Summary : Enables Brute Force To Bypass 2FA Email Verification due to nature of OTP, it contain only 6 digits which is valid till 24                     hour provide attacker so much time to exploit it


# August  
1) Vulnerability Disclosure (rulerfooo) (BugCrowd) (1-2 Weeks ~ 7 Days)  
   A) Partial Subdomain Takeover via Unclaimed Mailgun Domain - `Medium`
    - Result : Pending
    - Partial Subdomain Takeover
    - Summary : A Subdomain was pointing to a 3 party website(mailgun website) , but it require domain ownership to fully claim the domain.                    But able to partially claim it. Now no one can claim it again as already claim by me.
  
   B) Publicy Accessible phpinfo Page - `Low`
    - Result : Duplicate
    - Information Disclosure
    - Summary : phpinfo page prints out detailed information about system and the PHP configuration.
    - Ref - https://hackerone.com/reports/17514



2) Individual Bug-Bounty Program (droooo) (Internet) (3th Week)  
   A) OTP Verification Bypass in Email or Phone Update allows setting unverified email or number for OTP Delivery. - `Medium`
    - Result : Pending - Not Responding
    - Improper Authentication/Business Logic Flaw
    - Summary : Any Update Functionality in the App which require OTP to complete the task was not properly validating OTP on the server side.                 By Intercepting Response and modifying it like the request was successful, it was possible to change email, phone.                             Now can make the application to send OTPs to newly updated unverified Email and Phone to update the Password.                                  Or can simply used the same technique to change the password in the profile page.
                All the OTP Verifying endpoints was vulnerable to this technique even the login page, just that it require additional data                     from the server(JWT TOKEN) was unable to bypass login.



3) BugCrowd Vulnerability Disclosure (wedding) (4th Week)  
   A) Missing Email Ownership Validation Allows Registration With Unclaimed Email - `P5`
    - Result : P5 - Informational - Security Good Practice
    - Insufficient Security Configurability
    - Summary : The App is allowing to login with any email without checking user has its ownership or not. Later that email can be used to login even if don't                  have access to the mailbox , as can do login with set password or can receiver otp on mobile. Hence , it denial of service to the email real                     owner.
  
   B) Business Logic Issue: Mobile Number Uniqueness and Ownership Missing
    - Result : Pending
    - Business Logic Flaw
    - Summary : The application enforces uniqueness of mobile numbers only during registration, but fails to enforce the same rule in the about section of user.                 As a result, users can update their profile to use a mobile number that is already associated with another account. No OTP verification is                       performed to validate ownership of the updated number.
   
