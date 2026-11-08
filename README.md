# Brass & Blade Barbershop – Online Booking Website

**Midterm + Endterm Project – Web Development (HTML, CSS, Bootstrap, JavaScript, jQuery)**

## Team
- Bazaraly Ramazan
- Tolegen Zhassulan

## Live site
_Add your GitHub Pages / Netlify link here_

## Topic
A multi-page responsive website for a barbershop. Visitors can see the services and prices, choose a barber, and send a booking request online. The theme is a classic barbershop: navy, barber-pole red and brass colors, with Oswald (headings) and Source Sans 3 (text) fonts.

## Project structure
```
index.html      Home
services.html   Services & price table
barbers.html    Barbers
booking.html    Booking form
contact.html    Contact info & feedback form
css/style.css   Custom styles
js/app.js       JavaScript (data arrays, DOM, events, validation)
js/jq.js        jQuery (traversal, events, effects)
README.md
```

## How the project meets the requirements

### 1. General requirements
- 5 pages: Home, Services, Barbers, Book now, Contact.
- The same Bootstrap navbar is on every page; the current page is highlighted and the menu collapses into a burger button on mobile.
- Semantic HTML5, consistent indentation, comments in CSS.

### 2. HTML (10 pts)
- Headings `h1`–`h3` in correct order, paragraphs, lists (`ul` for opening hours), links, `address` for contacts.
- **Table:** price list on `services.html` (`caption`, `thead`, `tbody`, `th scope`).
- **Forms:** booking form (`booking.html`) with text, tel, select, date, time and textarea; feedback form (`contact.html`). All inputs have `label`s.
- Semantic tags: `header`, `nav`, `main`, `section`, `article`, `address`, `footer`.
- `div` is used for structure and wrappers; `span` for small inline highlights.

### 3. CSS (10 pts)
- Element, class and ID selectors (`#site-header`, `#hero`, `#price-table`, `.barber`, `.feature`).
- CSS variables (`--ink`, `--red`, `--brass`) keep colors consistent.
- **Flexbox:** feature cards and opening hours.
- **Grid:** barber cards (`grid-template-columns: repeat(4, 1fr)`).
- **Positioning:** `position: sticky` header, `position: absolute` for the striped line under the header and the specialty badges on barber cards, `relative` for their parent.

### 4. Responsive design & Bootstrap (15 pts)
- **Media queries:** `max-width: 992px` (tablet: barbers go to 2 columns, smaller hero title) and `max-width: 576px` (mobile: single column, feature cards stack).
- **Bootstrap grid:** `container`, `row`, `col-md-6`, `col-lg-7`, `col-sm-6`, gutters `g-3` / `g-4`.
- **Utilities:** spacing (`py-5`, `mb-3`, `mt-4`), text alignment (`text-center`, `text-md-end`), buttons (`btn`, `btn-lg`, `btn-outline-light`), form controls, `table-responsive`.

### 5. Creativity & presentation (10 pts)
- Barber-pole stripe, brass accents and real barbershop content (services, durations, prices in KZT, opening hours).
- Same colors, fonts and button style on all pages; simple navigation with a clear "Book now" path from every page.

### 6. Code quality & deployment (10 pts)
- One shared stylesheet, no repeated inline styles, clean indentation.
- Published online (link above).

### 7. Functionality (15 pts)
- All pages load and every navigation link works.
- Booking and feedback forms use HTML validation (`required`, input types, time limits). They do not send data to a server, because the course covers only HTML/CSS/Bootstrap.

## How to run locally
Open `index.html` in a browser. An internet connection is needed for Bootstrap and Google Fonts (CDN).

---

# Endterm update (JavaScript & jQuery)

The endterm extends the same barbershop site. The 5 pages, navigation, Bootstrap layout and midterm CSS are unchanged.

## New features
| Feature | Page | File |
|---|---|---|
| Services rendered from an array, **search** and **category filter** | Services | `app.js` |
| **Favorites list** with total price (add/remove DOM items, saved in localStorage) | Services | `app.js` |
| Barber cards generated from an array | Barbers | `app.js` |
| **Booking form validation** with messages under each field and a success message | Book now | `app.js` |
| Service/barber dropdowns filled from arrays, live price summary | Book now | `app.js` |
| **Contact form validation** (name, email format, message length) | Contact | `app.js` |
| **Dark/light theme switcher** (on every page, remembered) | All | `app.js` |
| jQuery: slide toggle on feature cards, barber bio accordion, table row highlight, character counter, back-to-top button | All | `jq.js` |

## Requirement checklist
- **Arrays:** `services`, `barbers`, `favorites`. **Loops:** `for...of` in `filterServices`, `forEach` for rendering cards, favorites and dropdowns.
- **Functions:** `formatPrice`, `findService` (returns object), `filterServices` (returns array), `validateRequired` (returns message), `setFieldState`, `showToast` and others.
- **DOM:** `createElement`/`appendChild`, `innerHTML`, `classList.toggle`, `textContent`, `hidden`; elements are added and removed (favorites items, toast).
- **Events:** `addEventListener` with `click`, `input`, `change`, `submit`, `keydown` (Escape clears search), `DOMContentLoaded`; `preventDefault()` on form submit.
- **Validation:** custom rules (`novalidate`), messages next to fields, no submission while errors remain, success alert.
- **jQuery:** selectors by ID (`#msg`), class (`.feature h3`), attribute (`a[href^="tel:"]`), descendant (`#price-table tbody tr`); traversal `next()`, `closest()`, `siblings()`, `find()`; events `click`, `input`, `scroll`; effects `slideToggle`, `slideUp`, `fadeIn`/`fadeOut`, `animate`.

## How to test
1. **Services:** type "beard" in search, change the category, press Esc in the search box. Click "Save" on a few cards; see the favorites list and total. Remove an item with the ✕ button. Click a table row to highlight it.
2. **Barbers:** click a card to open the bio; click another and the first one closes.
3. **Book now:** press "Request booking" with empty fields to see errors; try a past date or a Sunday; choose a service to see the price; fill everything correctly to see the success message.
4. **Contact:** type fewer than 10 characters in the message and send; enter an invalid email; watch the counter.
5. **Home:** click a feature title to collapse it. Scroll down and use the ↑ button.
6. Use the Dark mode button in the navbar on any page.
