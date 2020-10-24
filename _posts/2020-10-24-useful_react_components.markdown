---
layout: post
title:      "Useful React Components"
date:       2020-10-24 21:29:44 +0000
permalink:  useful_react_components
---



Hi all! After building a few websites with React, I came across a few components that are pretty useful and will help make your next application better and more visually appealing! In this article I will be explaining how to install them and how to implement in your projects.

## EmailJS

Have you ever wanted to create a contact form in your web application, that will allow messages to be sent to your email directly? EmaiJs is a simple to use component that will do just that! It’s super simple to set up and can be used with React, Vue.js, Angular, and even in Wix. To install this application in terminal run:

`npm install emailjs-com --save`


This will instal the SDK using npm, you can also use yarn too if you have that installed. Before we can add the code in your application you must set up an account at https://www.emailjs.com/. When you have your account set up click on “Add New Service” and select your email provider, I am using Gmail so select Gmail. On the next screen under Name enter “Gmail” and for Service ID “gmail”. Click through the next steps and be sure to “Allow” the use of EmailJS on your Gmail account. The next thing you must do is create an Email template so that when a user sends you a message the email will be formatted to the template that you have created. Once Saved we can start writing in the code!


After installing the SDK in your Contact component and setting up your account, import the ‘emailjs’ component as one of your imports in your ContactForm component.

```
import emailjs from 'emailjs-com';
import React from 'react';
```

From here you can create a form for your contact however you would like. Once you have your form set up. Create a function called sendEmai() and pass an argument event to it. This sendEmail function can be found on the Emailjs website. 

```
function sendEmail(e) {
    e.preventDefault();

    emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', e.target, 'YOUR_USER_ID')
      .then((result) => {
          console.log(result.text);
      }, (error) => {
          console.log(error.text);
      });
  }
```

There are a few things you need to replace here. The ‘YOUR_SERVICE_ID” will be replaced by “gmail”. “YOUR_TEMPLATE_ID” will be replaced by the Template ID of the email template you just created. These both can be found on the website under their respective pages. And finally “YOUR_USER_ID” can be found under the Integration tab under API keys. Copy and paste the User ID and replace that with “Your_User_ID” 

Once you have all that set up you’re all set! Be sure to pass the function into the form as an OnSubmit event. 

```
<form onSubmit={sendEmail}>
….
</form>
```

Test it out for yourself and you should be getting a message sent to your email in the format of your email template. If you want to read more on EmailJS visit https://www.emailjs.com/.

## Styled Components

I started to use Styled components more often since it gives me better organization and cleaner code. To use Styled Components install styled components with npm and yarn. 

```npm install styled-components --save```

Create an elements.js file with each of your components and import that elements file to it. so , for example if you have a ContactForm folder with index.js create an ContactFormElements.js file in the same folder. In the ContactFormElements you will be using the styled-components so import the component in there. 

```import styled from “styled-components”```

Now you can use styled components to style your components. An example of this can be used for the ContactFormContainer. 

```
export const ContactFormContainer = styled.div `
color:#fff; 
Background: #eeefbfb;
` 
```

In the index.js file import this styled component. 

```
import { ContactFormContainer} from “./ContactFormElements”
```

Now every time you use the <ContactFormContainer> tag it will be styled in the way that you had defined it. This makes it super easy and your code more readable. More information on Styled Components can be found on their website https://styled-components.com/

## React Scroll 

React Scroll is another handy component that will help animate the scroll down affect to the desired target location. This can be easily used by installing the component using npm or yarn.

```npm install react-scroll --save```

I used styled components to implement React Scroll so see the Styled-Components section for more information on how to utilize it. 

In your NavbarElements.js file you will import the ‘react-scroll’ component. You will use the react scroll component anywhere that you seem fit. But for this example I will use it in the NavBar component. 


`import {Link} from react-scroll`

A note here: Link is also used in react-router-dom so if you are using both make sure to rename the Link using the as keyword to something other than Link. 

Then create a Link component by the following: 

```
export const NavLinks = styled(Link)`
	color: #007cc7;
	cursor: pointer;
`
```

In the index,js file of your component. Import the animateScroll from “react-scroll” and the NavLink styled component. This will allow the scroll effect to the location on which link you click. 

```
import {animateScroll as Scroll} from “react-scroll”
import {NavLink} from “./NavbarElements.js”
```

And now in the <NavLink> component you can customize the scroll speed and where you would like the scrolls destination to be. 

```
…
<NavLink to=”about” smooth={true} duration={500} spy={true} exact=”true”>About</NavLink>
…
```

And just like that you have the scroll animation! Make sure you have those parameters in the <NavLink> for the scroll animation to work. You’re probably asking where do we use animateScroll? animateScroll can be used when clicking on the logo to go back to the top of the page. Create a function and set that function to an onClick event on the logo, or wherever you seem fit.  

```
const toggleHome=() =>{
	scroll.scrollToTop()
}
...
<NavLogo to=”/” onClick={toggleHome}>Fake Logo</NavLogo>
...
```

I hope that these few extra components will help make your next project easier and better! Happy Hacking!! 

