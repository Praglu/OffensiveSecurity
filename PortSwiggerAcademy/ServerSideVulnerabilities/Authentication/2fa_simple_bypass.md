# Lab: 2FA simple bypass
This lab's two-factor authentication can be bypassed. You have already obtained a valid username and password, but do not have access to the user's 2FA verification code. To solve the lab, access Carlos's account page.

- Your credentials: `wiener:peter`
- Victim's credentials `carlos:montoya`

## Walkthrough:
Let’s access the login page and see with Burp what’s hiding in the requests.
![1](images/lab2/1.png)

When we provide username and password, we are being asked for a 4-digit security code.
![2](images/lab2/2.png)

When we click on the Email client button, we are being redirected into another site, where we can get our 4-digits security code.
![3](images/lab2/3.png)

And with that code we can log into the application.
![4](images/lab2/4.png)

When we try logging as carlos, we also need to provide a 4-digits security code.
![5](images/lab2/5.png)

But if we click on the Email client button, we are being redirected into a site, where are wiener’s information. Can we use his code to log into another user?
![6](images/lab2/6.png)

Nope, that’s not possible.
![7](images/lab2/7.png)

Also, if we try changing id in the URL from wiener to carlos, we are being redirected into the login page.

So what else can we try? 


The task is to bypass the 2FA. Let’s login as carlos and simply change the URL (delete login2).

Look at that, it worked! All we had to do was go to another URL by simply removing login2 from the URL.
![8](images/lab2/8.png)

