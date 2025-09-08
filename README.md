 # MyPortfolio – Vue.js Project

### Project Setup

* Installed Vue 3 using Vue CLI

Initially struggled with Git config (username/email not set), which blocked project creation.

* Fixed with:

git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"

After reinstall, I had to add features individually (instead of selecting them during creation):

- Babel (browser compatibility)

- Router (for page navigation)

- Vuex (state management, reserved for future use)

- CSS Pre-processors (styling flexibility)

- Linter / Formatter (for clean, consistent code)

## Terminology I learnt:

To run in development:

npm install
npm run serve

To build for production:

npm run build

## Routing Setup

Three routes:

/ → HomePage

/about → AboutPage

/contact → ContactPage

Added NavBar with <router-link>s for switching between pages

# I learnt how to add screenshots to my readme file as seen below: 
## Screenshots

### Home Page
![Home Screenshot](./public/screenshots/HomePage.png)

### About Page
![Home Screenshot](./public/screenshots/AboutPage.png)

### Contact Page
![Contact Screenshot](./public/screenshots/ContactPage.png)


## Pages & Components

HomePage → Welcome page (name + intro)

AboutPage → My journey into front-end development

ContactPage → Contact form / contact info

NavBar → Navigation menu (links to all routes)

App.vue → Root layout that displays NavBar + <router-view>

## Challenges Faced

Git config problem

HelloWorld.vue kept showing → deleted and replaced with NavBar and routes

Case sensitivity (had to rename Views → views to match import paths)

ESLint errors about single-word component names → fixed by renaming to HomePage, AboutPage, ContactPage

Learnings & Customisations

Learned how to manually add Vue features after project creation

Got comfortable with Vue Router

Learned how ESLint rules enforce best practices (multi-word component names)

Practiced creating a responsive NavBar