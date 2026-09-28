# FindIt - Frontend

This is the user interface for **FindIt**, a classified ads platform built as our second-year project with **Nemo Technologies (Pvt) Ltd**. People can browse and post ads, while administrators use a dashboard to review listings and manage the platform.

The frontend is a Laravel application built with Blade, Bootstrap, and AJAX. It consumes the separate Laravel API in [`backend/`](../backend/README.md). See the [main project README](../README.md) for the full project story, team, and contributions.

## What it does

**For users**

- Browse ads and view their details
- Filter listings by district, town, price range, and category
- Sign in and post free or paid ads with images and details
- Save favourites, rate ads, and share listings

**For admins**

- Review and manage ads through the dashboard
- Search and filter listings
- Manage user accounts according to their role

## Project structure

| Folder | What's in it |
|---|---|
| `app/` | Frontend controllers, models, and application logic |
| `config/` | Frontend application settings |
| `public/` | Public images, CSS, JavaScript, and the web entry point |
| `resources/` | Blade templates and source assets |
| `routes/` | Web routes for frontend pages |
| `tests/` | Frontend tests |

## Getting it running

You will need PHP, Composer, Node.js/npm, and a running copy of the [backend](../backend/README.md). Use the versions required by this application's `composer.json` and `package.json`.

**1. Clone the project and enter the frontend app**

```sh
git clone https://github.com/Ishari-928/FindIT_Online_Advertisemet_System.git
cd FindIT_Online_Advertisemet_System/frontend
```

**2. Install dependencies and set up the environment**

```sh
composer install
cp .env.example .env
php artisan key:generate
npm install
```

Set `APP_URL` to the frontend address. Configure the backend API URL in `.env` using the variable expected by this application's configuration (the previous frontend setup uses `BACKEND_URL`). Keep the frontend and backend URLs consistent with the ports you start below.

**3. Build assets and start the frontend**

```sh
npm run dev
php artisan serve --port=8000
```

Run `npm run dev` in its own terminal if it stays active. Open `http://127.0.0.1:8000` after the backend is running on port `8008`.

> `.env` contains local settings and secrets. Create it from `.env.example`; do not commit it.

## Technologies

Laravel, Blade, Bootstrap, JavaScript, and AJAX. The frontend calls the backend API for authentication, listings, and administrative workflows.

## The team

This app was built by Ishari Abesooriya, Pasan Athuluwage, Wethma Sithumini, Ashini Hasara, and Basuru Jithmal. See the [main README](../README.md#the-team) for roles and profile links.

Thanks to **Nemo Technologies (Pvt) Ltd** for collaborating with us on the project.
