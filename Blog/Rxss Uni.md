- Here, I logged onto the uni auth site to enroll for the 2nd Year, and came across a parameter that I tested, which encoded ```<>```, but not ```"```. Which meant, I could still break out of the value using a double quote and still make it one click, with the following payload. 
(The autofocus/onfocus JS handler makes that possible)

```"onfocus=confirm(window.origin) autofocus="x"```

There were blocked attempts, the WAF picked up on open tags with common vectors:
```
<script
<img
<svg
etc..
```
<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/60fb4536-78c0-498d-81b0-ac8601753534" />


Although, low impact as auth wasn't local or session storage based so can't be accessed by JS. But it would've been believeable to phish uni students for user/pass as there's a popup for legit auth signin for students, I asked ChatGPT for more impact. 

I reported it ethically to my lecturer and it got fixed.

### PoC:
<video width="600" controls>
  <source src="/Assets/uni-rxss.mp4" type="video/mp4">
</video>
https://github.com/user-attachments/assets/0702f9d6-ee63-423f-984a-bdc48c543bab










