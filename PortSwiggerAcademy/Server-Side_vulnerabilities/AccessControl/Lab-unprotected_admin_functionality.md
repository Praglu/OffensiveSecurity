# Lab: Unprotected admin functionality
 This lab has an unprotected admin panel.

Solve the lab by deleting the user carlos. 

## Walkthrough:
At a first look, this site looks like a typical web shop. What comes to my eyes is the **My account** button on the right site. Let’s check it out.
![1](images/1.png)

There is a form for signing in. I doubt we know any account we can use for login.
![2](images/2.png)

There are no information in the source code. I don't think running **ffuf** here is necessary. 

Let's try with accessing the *robots.txt* file.
```javascript
/robots.txt
```

And we got something!
![3](images/3.png)

Now we know about an address *administrator-panel* that wasn't meant to be visible. So ... let's try accessing it! :grin:
![4](images/4.png)
Look at that. Now we’re able to access some functionalities, that, I would guess, shouldn’t be accessable as a non-administrator.

So let's delete **carlos** -> like we are supposed to do.

And thanks to that, the lab has been solved :white_check_mark:
![5](images/5.png)
