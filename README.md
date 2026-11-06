# Edaga

An early-stage e-commerce website skeleton: a React front end and a
Node.js/Express back end backed by MongoDB. The intended scope — product
listing, cart, authentication, checkout — is documented in
[`docs/project-outline.md`](docs/project-outline.md).

> **Status: work in progress.** The repository currently contains a top-level
> React shell, placeholder pages, and a server bootstrap. It is **not runnable
> yet** — see [Known gaps](#known-gaps).

## Repository layout

```
docs/project-outline.md   Feature and architecture outline for the store
src/index.js              React entry point (ReactDOM.render into #root)
src/App.js                Router shell wiring the page routes
src/components/Navbar.js  Top navigation between Home, Cart and Login
src/pages/HomePage.js     Placeholder home page
src/pages/CartPage.js     Placeholder cart page
src/pages/LoginPage.js    Placeholder login page
src/server.js             Express/ Mongoose server bootstrap
```

## Front-end routes

| Path     | Component    |
| -------- | ------------ |
| `/`      | `HomePage`   |
| `/cart`  | `CartPage`   |
| `/login` | `LoginPage`  |

Routing uses `react-router-dom` (`BrowserRouter`, `Switch`, `Route`).

## Back end

`src/server.js` connects to MongoDB through Mongoose and then starts the
Express app. The app module is expected at `./app` (not committed yet).

Environment variables:

| Variable    | Purpose                                   |
| ----------- | ----------------------------------------- |
| `PORT`      | HTTP port, defaults to `5000`             |
| `MONGO_URI` | MongoDB connection string (required)      |

## Prerequisites

- Node.js and npm (no version is pinned yet — there is no `package.json`)
- A running MongoDB instance for the back end

## Known gaps

These are the pieces needed before the project can be installed and run:

- **No dependency manifest.** A `package.json` is needed for `react`,
  `react-dom`, `react-router-dom`, `express` and `mongoose`.
- **No HTML entry template.** `public/index.html` with a `#root` element is
  missing; `src/index.js` mounts into it.
- **Missing server app module.** `src/server.js` requires `./app`, which is not
  in the repository.
- **Placeholder UI only.** The pages render static headings; product listing,
  cart state, authentication and checkout are not implemented.
- **No tests and no license file.**

## Contributing

Work on a topic branch and open a pull request against `main`. Keep the
outline in `docs/project-outline.md` up to date when the intended scope
changes.
