# My Website

Personal portfolio in which CV, hobbies and contacts pages are built through some themes related to astronomy: a rotating 3D celestial sphere, the constellation of Leo, and a signal to send.

Everything is **HTML and CSS (Sass)**, without  JavaScript.

<br>

<div align="center">

## LINK: https://carola1991.github.io

</div>

<br>

---

### CV · The Celestial Sphere (home)

Page constructed with a celestial sphere in the center enclosing my CV symbolized by five constellations, representing different categories; each constellation can be brought to the foreground with a click, illuminating the corresponding list placed next to it.


### CV as plain text (printable)

The possibility of having the CV in printable version has been implemented.

### Hobbies · The Constellation of Leo

On this page, the stars in my constellation (Leo) hide my interests in the individual categories indicated.

### Contact

On this page through a form you can send me a message or visit my social media profiles.

---

##  Project description

The site has three main pages, plus a plain-text version of the CV:

| Page | File | Idea |
|---|---|---|
| **CV** | `index.html` | A **sphere** rotates in the middle with five constellations: *Bachelor's & Master's Degree*, *Training course*, *IT Skills*, *Soft skills* and *Work Experience*. On the sides, the **fixed lists** of the sub-categories, joined to the sphere by beams of light. Hovering or tapping a constellation stops the sphere, brings that constellation to the front and **lights up its list**. |
| **CV (text)** | `cv.html` | The same CV in a **linear, easy-to-read** form (`section`, `article`, `time`), with a **print stylesheet** for a clean PDF. |
| **Hobbies** | `hobbies.html` | The **constellation of Leo**, drawn from real celestial coordinates: every star is a hobby. One click opens, on the same page, a panel with the **mini-constellation of sub-categories**. |
| **Contact** | `contact.html` | A form (with required fields and native validation) and social links, centered. |


##  Features

**Celestial Sphere (CV)**
- Continuous rotation, paused on mouse hover, touch or keyboard focus
- The constellation in the foreground turns to face the viewer (*billboarding*): text never ends up upside down
- Depth: the far side is darker and blurred; the lines light up when a constellation is close
- Line thickness and brightness follow how closely two skills are related
- Armillary rings, bridges between constellations, an orbit with a satellite, shooting stars, cosmic dust, pulsing stars
- **Auto** and **Pause rotation** buttons

**Pages and content**
- **Sticky** navigation menu, hamburger menu on mobile with **no JavaScript**
- Printable text version of the CV
- Contact form ready to connect to Formspree 

**Quality**
- 100% responsive (relative units, `clamp()`, container queries, breakpoints at 576 / 768 / 992 / 1200 px)
- `prefers-reduced-motion` respected; fallback for browsers without `:has()`
- Semantic markup: `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`, `time`
- A different meta description and Open Graph tags for every page

---

##  Technologies

| Requirement | Choice |
|---|---|
| Front-end framework | **Bootstrap 5.3** (CSS only, no JavaScript bundle) and Bootstrap Icons |
| CSS | **Sass (SCSS)**, split into partials and imported with `@use` |
| Layout | **Flexbox** (header, menu, social links, buttons) and **CSS Grid** (CV grid, contact, cards) |
| Sticky menu | `sticky-top` at every breakpoint; hamburger menu built with a checkbox and `:checked` |
| Favicon | `favicon.jpg` |
| Fonts | **IBM Plex Serif** italic for text, **IBM Plex Mono** for menu, buttons and labels (Google Fonts) |
| Colors | Midnight-blue background, yellow-white text, categories in shades of blue |

---

##  Project structure

```

├── index.html                # CV: the celestial sphere (home)
├── pages/
│   ├──cv.html                # CV as plain text, printable
│   ├──hobbies.html           # Hobbies: Leo and the sub-categories
│   ├──contact.html           # Contact: form and social links
├── assets/
│   ├──images
│       ├── avatar.jpg        # my photo
│       ├── favicon.jpg
│   ├── css/
│       └── style.css         # CSS compiled from scss/
│   ├── scss/
│       ├── style.scss        # entry point (@use of the partials)
│       ├── _variables.scss   # colors, fonts, breakpoints, categories
│       ├── _mixins.scss      # up, down, halo, mono, nav-surface, ...
│       ├── _base.scss        # reset, body, headings, footer
│       ├── _header.scss      # header and menu
│       ├── _stars.scss       # shared stars and lines
│       ├── _sphere.scss      # the 3D sphere
│       ├── _cv-map.scss      # CV grid, side lists, buttons
│       ├── _cv.scss          # CV as plain text
│       ├── _hobbies.scss     # Leo and the hobby panels
│       ├── _contact.scss     # form and social links
│       └── _print.scss       # print stylesheet
├── README.md                 # in English

```

---

##  Running it locally

No installation needed: **open `index.html` in your browser** (an internet connection is required for Bootstrap and the fonts).

To change the styles:

```bash
# 1. install Sass (once)
npm install -g sass

# 2. compile the SCSS into CSS
sass assets/scss/style.scss assets/css/style.css

# or recompile every time you save
sass --watch assets/scss/style.scss assets/css/style.css
```

> `assets/css/style.css` is a generated file: always edit the `.scss` files and recompile.

---


##  Compatibility and limits

- **Recommended browsers**: recent versions of Chrome, Edge, Safari and Firefox (roughly Chrome/Edge 119+, Safari 16.5+, Firefox 128+). The site uses modern CSS features: `:has()`, `@property`, container queries, `:user-invalid`. In older browsers the sphere may not rotate; without `:has()` it still pauses on mouse hover.
- **Accessibility**: the sphere is decorative (`aria-hidden`) and the same information is in the side lists and in `cv.html`. The hobby panels use `role="dialog"` but, without JavaScript, **do not manage focus** or the Esc key.
- **Mobile menu**: the hamburger menu works with a checkbox, so `aria-expanded` is not updated.
- **Form**: it sends data via Formspree.
- **Content**: names, dates, companies, skills and social links are **placeholders** to replace.
- **Testing**: to be checked on more browsers and real devices.

---

## Credits

- [Bootstrap](https://getbootstrap.com) and [Bootstrap Icons](https://icons.getbootstrap.com)
- [IBM Plex](https://www.ibm.com/plex/) via [Google Fonts](https://fonts.google.com)
- Star positions of Leo: celestial coordinates (right ascension and declination)


##  Author

**Carola D'Orsi** 