# Frontend Mentor - Easybank landing page solution

This is a solution to the [Easybank landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/easybank-landing-page-WaUhkoDN). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page

### Screenshot

(./screenshots/easybank_mobile_full.png)
(./screenshots/easybank_mobile_view.PNG)
(./screenshots/easybank_mobile_nav.PNG)
(./screenshots/easybank_a_1200px.PNG)
(./screenshots/easybank_b_1200px.PNG)
(./screenshots/easybank_c_1200px.PNG)
(./screenshots/easybank_d_1200px.PNG)


### Links

- Solution URL: [https://www.w3schools.com/]
- Live Site URL: [https://easybank-mu-ruddy.vercel.app/]



## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Mobile-first workflow
- CSS Grid

### What I learned

Creating the navigation for mobile with the dark overlay was a bit tricky. After writing the code for the overlay and Nav and giving it a FIXED position, I had a problem with the navbar and the fact that setting fixed as the Position made the width readjust. So, instead of using Position: FIXED for the navbar, I used " Position: -webkit-sticky; Position: sticky; top: 0px; "  which worked properly/Synced with the fixed position added to the Nav.

```html


<img src="images/icon-hamburger.svg" alt="burger-menu" class="burger-menu" id="burger-menu">
                
<img src="images/icon-close.svg" alt="Exit Button" id="exit-button" class="exit-button">

<div class="navbar">
        <div class="container">

            <header>
                <a href="#"><img src="images/logo.svg" alt="Easybank Logo" class="logo"></a>
            </header>

            <img src="images/icon-hamburger.svg" alt="burger-menu" class="burger-menu" id="burger-menu">
                
            <img src="images/icon-close.svg" alt="Exit Button" id="exit-button" class="exit-button">

    
            <nav>
    
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Careers</a></li>
                    
                    
                </ul>

                <ul>
                    <li><button class="request-cta">Request Invite</a></button>
                </ul>
    
            </nav>

        </div>

    </div>

<div class="nav-overlay" id="nav-overlay"></div>

```


```scss

.exit-button , nav , .nav-overlay{
    display: none;
}

.burger-menu{
    display: block;
}

.navbar{
    position: -webkit-sticky;
    position: sticky; top: 0px;
    background: var(--white);
    padding: 1em;
    place-content: space-between;
    z-index: 99;

div.nav-overlay {
    position: fixed;
    background: rgba(0, 0, 0, .8);
    height: 100vh;
    width: 100%;
    z-index: 0;
}

nav{
    position: fixed;
    top: 5em;
    text-align: center;
    background: var(--white);
    border-radius: 5px;
    padding: 2em 19%;
    width: 50%;
    animation: fadeIn 1s forwards;

    a{
        color: var(--dark-blue);
        font-weight: 400;
    }

    li{
        margin: 1em;
    }

    
}

@keyframes fadeIn {
    from{
        opacity: 0;
        transform: translateY(-2em); 
    }

    to{
        opacity: 1;
        transform: translateY(0);
    }
}

```


```js

const menuBtn = document.getElementById('burger-menu');
                closeBtn = document.getElementById('exit-button');
                overlay = document.getElementById('nav-overlay');
                nav = document.querySelector('nav');


          menuBtn.addEventListener('click', () => {
              nav.classList.add('burger-menu');
              closeBtn.classList.add('burger-menu');
              overlay.classList.add('burger-menu');

              menuBtn.style.display = 'none';

          });

          closeBtn.addEventListener('click', () => {
              nav.classList.remove('burger-menu');
              closeBtn.classList.remove('burger-menu');
              overlay.classList.remove('burger-menu');

              menuBtn.style.display = 'block';


          });
```


### Continued development

Going further, I would like to make my work more responsive and have less code in them. Had some issues when I started working on the bigger screens (Started with Mobile-first workflow) as I had to adjust some parts of code multiple times which felt like untieing a lot of shoe laces😅.

### Useful resources

- [CSS Tricks](https://css-tricks.com/) - This helped me with griding sections of my work, making those sections the easiest part of the project. I'd recommend it to anyone still learning this concept.


## Author

- Website - [Ayooluwatomide Komolafe](https://easybank-mu-ruddy.vercel.app/)
- Frontend Mentor - [@Ayooluwatomide](https://www.frontendmentor.io/profile/Ayooluwatomide)
- Twitter - [@ayooluwatomide_](https://www.twitter.com/ayooluwatomide_)