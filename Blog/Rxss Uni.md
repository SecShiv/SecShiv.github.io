### Reflected XSS on my Uni site.

- Here, I logged onto the uni auth site to enroll for the 2nd Year, and came across a parameter that I tested, which encoded ```<>```, but not ```"```. Which meant, I could still break out of the value using a double quote and still make it one click, with the following payload. 
(The autofocus/onfocus JS handler makes that possible)

```"onfocus=confirm(window.origin) autofocus="x"```

There were blocked attempts such as using:
```
<script
<img
<svg
etc..
```

- Although, low impact as auth wasn't local or session storage based so can't be accessed by JS. But it would've been believeable to phish uni students for user/pass as there's a popup for legit auth signin for students.

