# HTML + CSS Recap (Quick)

## HTML essentials
- **Boilerplate**:
  - `<!doctype html>`, `<html>`, `<head>`, `<body>`
- **Common tags**: `h1..h6`, `p`, `a`, `img`, `ul/ol/li`, `div`, `span`
- **Attributes**:
  - `id` (unique), `class` (reusable)
  - `href` for links, `src` + `alt` for images

### Forms (often used with JS)
- Inputs: `text`, `email`, `password`, `number`, `checkbox`, `radio`
- Important: `name`, `value`, `required`, `min`, `max`
- Submit: `<button type="submit">`

**Example**
```html
<form id="loginForm">
  <input id="email" type="email" required />
  <button type="submit">Login</button>
</form>
```

## CSS essentials
- Selectors:
  - Element: `p {}`  
  - Class: `.card {}`  
  - ID: `#header {}`
- Box model: **content → padding → border → margin**
- Display:
  - `block`, `inline`, `inline-block`
- Layout:
  - **Flexbox** (common in slides): `display:flex`, `justify-content`, `align-items`, `gap`
- Responsive:
  - Media query: `@media (max-width: 600px) { ... }`

**Example (flex + responsive)**
```css
.container { display: flex; gap: 12px; }
@media (max-width: 600px) {
  .container { flex-direction: column; }
}
```
