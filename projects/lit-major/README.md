# Lit Major

## Description
Lit Major is a small, personal application that can be used to track reading goals, progress, and book ownership. It can be used for one person or a small group of friends and/or family to share what they are reading and review books.

## Why Lit Major
I got tired of using goodreads.

I tried using a few other apps, but there are just some things they don't offer that I want in a book tracking app. I want to have a small app that I can use to track mine and my wifes book collection, track our reading goals and progress, and keep a record of the books we have read and what we thought of them. I also want to be able to share it with extended family that I care about and want to share books and reviews with.

The reason it is called Lit Major is because it cares a lot about books, but won't make any money (lol... sorry).

## Feature Wishlist
* Personally hostable on something like a personal computer or a Raspberry Pi
* A barcode scanner to add books to personal collection without having to manually search
* Sharable with friends and family
* Able to set annual reading goals
* Keep track of books read and TBR
* Able to rate the books read
* The ability to see if any other shared users have a book in their collection
    * Think of it like seeing who in your friends list owns a game on steam
* An option to hide a book from your read list or library
    * Still shows up for you, just with some symbology that indicates it is hidden from others
    * Book still counts towards annual reading challenge
    * Does not apppear in your list when someone else looks at it
* "Fave 5" book list to display on user profile
    * Like old myspace 
* Lending tracker
    * See who has your books
* Quote book
    * Keep a record of quotes you love in your reading
    * Access in an easily searchable format
    * Maybe display one to user daily?

## Features to condiser
* Should there be a "For You Page"?
    * Should there be a feed of what family and friends are reading?
    * What should it show?
    * Comments?
* Should you set a user name or just use your regular name?
* Purchase wishlist?


## Framework and Development
I think I want to make this a progressive web app. This should allow me to maintain only one code base and have it accessable as an application on phones and as a webpage on desktop.

I don't know what framework I want to use for the front end yet, but I have a few options.

### Documentation on Progressive Web Apps (PWAs)
* [Overview of Progressive Web Apps](https://learn.microsoft.com/en-us/microsoft-edge/progressive-web-apps/)
* [Progressive Web Apps by web.dev](https://web.dev/learn/pwa/progressive-web-apps/)
* [Angular VS React VS Vue](https://www.browserstack.com/guide/angular-vs-react-vs-vue)

### React
Developed by Facebook, this JavaScript library builds fast, interactive UIs with a component-based architecture.

It is the most widely used JavaScript-based library because of the ease it provides in creating web applications. Moreover, besides creating UI, it offers several features, such as Flux and React Native. One of the biggest advantages of using React is that you can create web as well as mobile applications using the same codebase with a framework called React Native. Each component of a a react application serves as a building block, making the application highly reusable. Reusable components in JavaScript recude development time and complexity.

Advantages:
* Reusable Components:
    * While developing React applications, the amount of complexity and coding is less.
    * It is also easy to maintain.
* Performance:
    * React does not depend upon the conventional DOM and uses a JavaScript structure, virtual DOM.
* Learning Curve:
    * React is way ahead of its competitors due to its easy learning curve.
    * It is easy for web developers who ahve just finished their concepts in HTML and JavaScript to learn React.

Limitations:
* Development Pace:
    * Since React is the most widely used library, it offers constant updates, which led developers to relearn newer concepts and get along with the pace of React.
* Into to JSX:
    * Learning React does not require any prerequisite. However, JSX does not come in handy to a lot of developers while learning React development.

When to use React (according to BrowserStack):
* When developing real-time, interactive applications such as social media platforms or live dashboards.
* When building single-page applications that require fast, seamless user interactions.
* When the project demands quick rendering and updates, especially with large lists or complex DOM structures.

### Vue
Vue is an open-source progressive frontend framework that came into wide popularity for creaing Single Page Applications (SPAs). SPAs are web applications that only have one HTML file rendering the entire code. Vue fcuses on beginner developers helping them create dynamic web applications without having to go through any prior tedious learning.

Advantages:
* Short Learning Curve:
    * React requires TypeScript, Vue is beginner-friendly and does not mandate any prior skills.
* Forums and Community:

Limitations:
* Ecosystem:
    * Vue has a very narrow ecosystem and does not render in older versions of browsers and operating systems.

When to use Vue (according to BrowserStack):
* When developing small to medium-sized projects that need efficient updates without large overhead.
* When creating customizable, reusable UI components that can be easily managed and integrated into different app parts.
* The app needs to be highly interactive, but doesn't require the full scale of heavier frameworks.

### Thoughts on the Matter
Pros of React:
* It is very popular in industry and will be the most likely to impress possible employers.
* It is widely adopted and works well with plenty of documentation and tutorials.

Cons of React:
* It is bigger and bulkier.

Pros of Vue:
* Fully made by open source community.
* Excellent documentaion.
* Especially made for newcomers.

Cons of Vue:
* Less likely to be fully usable in industry due to lower adoption rates.

Thoughts:
I am currently leaning towards Vue due it it being especially made for beginners. It seems to be a good option for small to medium projects, which I would consider mine to be. React seems like it would be more relevant of a skill to learn for my resume, but I am a big proponent of the FOSS community, and it seems like there is a lot of community support for Vue.
