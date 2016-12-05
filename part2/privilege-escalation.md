# Privilege escalation

> Most computer systems are designed for use with multiple users.
> Privileges mean what a user is permitted to do. Common privileges
> include viewing and editing files, or modifying system files.
>
> Privilege escalation means a user receives privileges they are not
> entitled to. These privileges can be used to delete files, view
> private information, or install unwanted programs such as viruses. It
> usually occurs when a system has a bug that allows security to be
> bypassed or, alternatively, has flawed design assumptions about how it
> will be used. Privilege escalation occurs in two forms:
>
> * Vertical privilege escalation, also known as _privilege elevation_,
>   where a lower privilege user or application accesses functions or
>   content reserved for higher privilege users or applications (e.g.
>   Internet Banking users can access site administrative functions or
>   the password for a smartphone can be bypassed.)
> * Horizontal privilege escalation, where a normal user accesses
>   functions or content reserved for other normal users (e.g. Internet
>   Banking User A accesses the Internet bank account of User B)[^1]

## Challenges covered in this chapter

| Challenge                                                                                   | Difficulty |
|:--------------------------------------------------------------------------------------------|:-----------|
| Access the administration section of the store.                                             | 1 of 5     |
| Get rid of all 5-star customer feedback.                                                    | 1 of 5     |
| Change the href of the link within the O-Saft product description into http://kimminich.de. | 3 of 5     |
| Access someone else's basket.                                                               | 2 of 5     |
| Post some feedback in another users name.                                                   | 3 of 5     |

### Access the administration section of the store {#adminSectionChallenge}

Just like the score board, the admin section was not part of your "happy
path" tour because there seems to be no link to that section either.

#### Hints

* Knowing it exists, you can simply _guess_ what URL the admin section
  might have.
* Alternatively, you can try to find a reference or clue within the
  parts of the application that are _not usually visible_ in the browser
* It is just slightly harder to find than the score board link

### Get rid of all 5-star customer feedback {#fiveStarFeedbackChallenge}

If you successfully solved above
[admin section challenge](#adminSectionChallenge) deleting the 5-star
feedback is very easy.

#### Hints

* Nothing happens when you try to delete feedback entries? Check the
  Javascript console for errors!

### Change the href of the link within the O-Saft product description {#changeProductChallenge}

The _OWASP SSL Advanced Forensic Tool (O-Saft)_ product has a link in
its description that leads to that projects wiki page. In this challenge
you are supposed to change that link so that it will send you to
http://kimminich.de instead. It is important to exactly follow the
challenge instruction to make it light up green on the score board:

* Original link tag in the description: `<a
  href="https://www.owasp.org/index.php/O-Saft"
  target="_blank">More...</a>`
* Expected link tag in the description: `<a href="http://kimminich.de"
  target="_blank">More...</a>`

#### Hints

* _Theoretically_ there are three possible ways to beat this challenge:
    * Finding an administrative functionality in the web application
      that lets you change product data
    * Looking for possible holes in the RESTful API that would allow you
      to update a product
    * Attempting an SQL Injection attack that sneaks in an `UPDATE`
      statement on product data
* _In practice_ two of these three ways should turn out to be dead ends

### Access someone else's basket

#### Hints

### Post some feedback in another users name

#### Hints

---

[^1]: https://en.wikipedia.org/wiki/Privilege_escalation