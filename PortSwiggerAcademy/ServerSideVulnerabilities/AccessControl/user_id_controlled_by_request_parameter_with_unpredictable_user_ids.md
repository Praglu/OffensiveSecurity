# Lab: User ID controlled by request parameter, with unpredictable user IDs
This lab has a horizontal privilege escalation vulnerability on the user account page, but identifies users with GUIDs.

To solve the lab, find the GUID for `carlos`, then submit his API key as the solution.

You can log in to your own account using the following credentials: `wiener:peter`

## Walktrough:
Let’s check the site.
![1](images/lab4/1.png)

In this lab we have to abuse an IDOR vulnerability, so let’s go to the login page and use given credentials.
![2](images/lab4/2.png)

After logging in we can see 2 things:

- GUID in URL,
- API key.

There is probably no way we guess GUID from carlos. So let’s think what can we do.
![3](images/lab4/3.png)

I think that the best solution will be to use Burp Suite and see whether we can see something interesting in the requests.

Unfortunately there was nothing hidden in the requests, so we gotta dig somewhere else. Let’s try exploring the applicaiton more. I didn’t pay attention to the home site, so let’s go back there.

When we explore a post, we can see that it was written by carlos (bottom of the picture). Also it is clickable. Let’s check it.
![4](images/lab4/4.png)

That’s interesting! Can you see what happened after clicking on carlos → post’s editor?
![5](images/lab4/5.png)

Okay, let’s copy the GUID from the url and try pasting it in the user panel.
![6](images/lab4/6.png)

Okay, that worked!
![7](images/lab4/7.png)

Now all we have to do is copy carlos’s API Key and submit it.
![8](images/lab4/8.png)

And that’s how the lab has been solved!
![9](images/lab4/9.png)

