# Vue 3 Vite Wedding Site — Template

This canvas contains a complete **Vue 3 + Vite** project scaffold for a wedding website. Files are included below; each file contains clear `/* EDIT HERE */` or `<!-- EDIT HERE -->` markers where you should replace names, dates, locations, text, images, and colors.

---

## Project structure

```
vue-wedding-site-template/
├─ package.json
├─ vite.config.js
├─ index.html
├─ README.md
├─ public/
│  └─ placeholder.jpg
└─ src/
   ├─ main.js
   ├─ assets/
   │  └─ placeholder.jpg
   ├─ App.vue
   ├─ styles.css
   └─ components/
      ├─ Hero.vue
      ├─ EventDetails.vue
      ├─ Gallery.vue
      └─ RSVPForm.vue
```

---

> **How to use:** Copy each file into a new local folder, run `npm install`, then `npm run dev` to preview. For deployment to GitHub Pages, see the `README.md` below.

---

## README.md

```md
# Vue Wedding Site Template

Minimal Vue 3 + Vite wedding website template.

## Local dev

1. Install dependencies:

```bash
npm install
```

2. Run dev server:

```bash
npm run dev
```

3. Build for production:

```bash
npm run build
```

## Deploy to GitHub Pages (simple)

1. Create a GitHub repository (public) and push the project.
2. In `package.json`, there is a `homepage` field you can set to `https://<yourusername>.github.io/<reponame>` (optional).
3. Build: `npm run build`.
4. Create a branch named `gh-pages` and push `dist/` contents to it, or use a GitHub Action to deploy `dist/` to GitHub Pages.

(If you want, I can provide an example GitHub Action to auto-deploy on push.)

## Where to edit

Look for `/* EDIT HERE */` and `<!-- EDIT HERE -->` comments inside components to change names, date, location, colors, and images.

---
```

---

## package.json

```json
{
  "name": "vue-wedding-site-template",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "vue": "^3.3.0"
  },
  "devDependencies": {
    "vite": "^5.0.0"
  }
}
```

---

## vite.config.js

```js
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

export default defineConfig({
  plugins: [vue()],
  base: './' // important for GitHub Pages relative paths
})
```

---

## index.html

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Name1 & Name2 — Wedding</title> <!-- EDIT HERE: page title -->
  </head>
  <body>
    <div id="app"></div>
    <script type="module" src="/src/main.js"></script>
  </body>
</html>
```

---

## public/placeholder.jpg

> A simple placeholder image is provided (copy any image you like into `public/placeholder.jpg` or `src/assets/placeholder.jpg`).

---

## src/main.js

```js
import { createApp } from 'vue'
import App from './App.vue'
import './styles.css'

createApp(App).mount('#app')
```

---

## src/styles.css

```css
:root{
  --accent: #f7d1cd; /* EDIT HERE: primary (blush) */
  --accent-2: #fff8f6; /* EDIT HERE: secondary (ivory) */
  --text: #333333;
  --muted: #6b6b6b;
  --container-width: 900px;
}

*{box-sizing:border-box}
body{
  font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
  margin:0;
  color:var(--text);
  background:linear-gradient(180deg,var(--accent-2),#ffffff);
}

.container{
  max-width:var(--container-width);
  margin:0 auto;
  padding:24px;
}

.header{
  text-align:center;
  padding:48px 0 12px;
}

h1.hero-title{font-size:2.4rem; margin:0}
p.lead{color:var(--muted); margin-top:8px}

.card{
  background:white;
  border-radius:12px;
  padding:18px;
  box-shadow:0 6px 20px rgba(0,0,0,0.06);
  margin-bottom:18px;
}

.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:16px}

.gallery img{width:100%;height:200px;object-fit:cover;border-radius:8px}

.rsvp-form label{display:block;margin-top:8px;font-weight:600}
.rsvp-form input,.rsvp-form textarea,.rsvp-form select{width:100%;padding:8px;margin-top:6px;border-radius:8px;border:1px solid #e6e6e6}

.btn{
  display:inline-block;padding:10px 18px;border-radius:10px;background:var(--accent);color:#111;font-weight:700;border:none;cursor:pointer;margin-top:12px;text-decoration:none
}

.footer{padding:24px 0;text-align:center;color:var(--muted)}
```

---

## src/App.vue

```vue
<template>
  <div>
    <header class="header">
      <div class="container">
        <h1 class="hero-title">Name1 & Name2</h1> <!-- EDIT HERE: couple names -->
        <p class="lead">"Date" • "Wedding location"</p> <!-- EDIT HERE: date and location -->
      </div>
    </header>

    <main class="container">
      <section class="card">
        <Hero />
      </section>

      <section class="card">
        <EventDetails />
      </section>

      <section class="card">
        <Gallery />
      </section>

      <section class="card">
        <RSVPForm />
      </section>

      <footer class="footer">
        <p>Made with ❤️ — replace this text in <code>src/App.vue</code>. <!-- EDIT HERE: footer text --></p>
      </footer>
    </main>
  </div>
</template>

<script>
import Hero from './components/Hero.vue'
import EventDetails from './components/EventDetails.vue'
import Gallery from './components/Gallery.vue'
import RSVPForm from './components/RSVPForm.vue'

export default {
  components: { Hero, EventDetails, Gallery, RSVPForm }
}
</script>
```

---

## src/components/Hero.vue

```vue
<template>
  <div class="grid">
    <div>
      <h2 style="margin:0">We are getting married</h2>
      <p class="lead">Please join us to celebrate our wedding day.</p>
      <p style="margin-top:12px">When: <strong>"Date"</strong></p> <!-- EDIT HERE: date -->
      <p>Where: <strong>"Wedding location"</strong></p> <!-- EDIT HERE: location -->
    </div>
    <div>
      <img src="/src/assets/placeholder.jpg" alt="couple" style="width:100%;border-radius:8px;" />
      <!-- EDIT HERE: replace image at src/assets/placeholder.jpg -->
    </div>
  </div>
</template>

<script>
export default { name: 'Hero' }
</script>
```

---

## src/components/EventDetails.vue

```vue
<template>
  <div>
    <h3>Event Details</h3>
    <div class="grid">
      <div>
        <h4>Ceremony</h4>
        <p>Time: 3:00 PM</p> <!-- EDIT HERE: ceremony time -->
        <p>Venue: "Wedding location"</p> <!-- EDIT HERE: venue address -->
      </div>
      <div>
        <h4>Reception</h4>
        <p>Time: 5:00 PM</p> <!-- EDIT HERE: reception time -->
        <p>Venue: "Reception location or same as ceremony"</p> <!-- EDIT HERE -->
      </div>
    </div>
  </div>
</template>

<script>
export default { name: 'EventDetails' }
</script>
```

---

## src/components/Gallery.vue

```vue
<template>
  <div>
    <h3>Gallery</h3>
    <div class="gallery grid">
      <!-- EDIT HERE: replace the images with your own by putting them in src/assets/ and changing the src values -->
      <img src="/src/assets/placeholder.jpg" alt="photo 1" />
      <img src="/src/assets/placeholder.jpg" alt="photo 2" />
      <img src="/src/assets/placeholder.jpg" alt="photo 3" />
      <img src="/src/assets/placeholder.jpg" alt="photo 4" />
    </div>
  </div>
</template>

<script>
export default { name: 'Gallery' }
</script>
```

---

## src/components/RSVPForm.vue

```vue
<template>
  <div>
    <h3>RSVP</h3>
    <form class="rsvp-form" @submit.prevent="onSubmit">
      <label for="name">Full name</label>
      <input id="name" v-model="form.name" required />

      <label for="email">Email</label>
      <input id="email" type="email" v-model="form.email" required />

      <label for="attending">Will you attend?</label>
      <select id="attending" v-model="form.attending">
        <option value="yes">Yes</option>
        <option value="no">No</option>
        <option value="maybe">Maybe</option>
      </select>

      <label for="message">Message (optional)</label>
      <textarea id="message" rows="3" v-model="form.message"></textarea>

      <button class="btn" type="submit">Send RSVP</button>

      <p v-if="status" style="margin-top:8px">{{ status }}</p>

      <p style="margin-top:12px;font-size:0.9rem;color:var(--muted)">
        NOTE: This template does not include backend storage. To capture RSVPs you can:
        <ul>
          <li>Use a service like Google Forms, Typeform, or Airtable (with their embed code).</li>
          <li>Use an email-to-form service (Formspree, Getform) — replace `onSubmit` to POST to their endpoint.</li>
          <li>Or I can add a GitHub Action / serverless function example to save responses if you want.
        </li>
      </p>
    </form>
  </div>
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  name: 'RSVPForm',
  setup() {
    const form = reactive({ name: '', email: '', attending: 'yes', message: '' })
    const status = ref('')

    function onSubmit() {
      // EDIT HERE: replace this with a POST to Formspree / Getform / your backend
      console.log('RSVP submitted', JSON.parse(JSON.stringify(form)))
      status.value = 'Thanks — your RSVP has been recorded locally (replace this behavior in code).'
      // clear the form optionally
      form.name = ''
      form.email = ''
      form.attending = 'yes'
      form.message = ''
    }

    return { form, onSubmit, status }
  }
}
</script>
```

---

## src/assets/placeholder.jpg

> Replace this file with your own photos. You can copy images into `src/assets/` and update component `img` src paths accordingly.

---

## Final notes

- Every place where you should change content uses clear `EDIT HERE` labels in HTML/JS/CSS.
- Colors are defined in `src/styles.css` at the top — change `--accent` and `--accent-2` for palette changes.
- For images, swap `src/assets/placeholder.jpg` with your own filenames.
- If you want a prettier layout, I can convert styles to Tailwind CSS or add animations.

---

Enjoy — open the code files in the canvas, copy them into a new repository, and tell me if you want an automated GitHub Action to deploy to Pages.
