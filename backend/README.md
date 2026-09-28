# FindIt - Backend

This is the API for **FindIt**, a classified ads platform built as our second-year project with **Nemo Technologies (Pvt) Ltd**. It handles authentication, ads, moderation, and the data used by the separate Laravel [frontend](../frontend/README.md).

The backend is a Laravel application. See the [main project README](../README.md) for the full project story, team, and contributions.

## What it does

**For users**

- Supports account access and ad posting
- Stores listing details and images, with AWS S3 used for ad images
- Provides ad search and filtering by location, category, and price
- Supports favourites, ratings, and paid ad workflows

**For admins**

- Provides tools to review, approve, reject, and remove ads
- Supports user and category management according to admin roles
- Serves filtered listing data to the admin dashboard

## Project structure

| Folder | What's in it |
|---|---|
| `app/` | Controllers, models, middleware, and application logic |
| `config/` | Database, mail, storage, session, and other settings |
| `database/` | Migrations, factories, and seeders |
| `public/` | Web entry point and public assets |
| `resources/` | Views and other application resources |
| `routes/` | API and web route definitions |
| `storage/` | Logs, cache, and local application storage |
| `tests/` | Unit and feature tests |

## Getting it running

You will need PHP, Composer, and MySQL. Use the versions required by `composer.json` and the project's database configuration.

**1. Clone the project and enter the backend app**

```sh
git clone https://github.com/Ishari-928/FindIT_Online_Advertisemet_System.git
cd FindIT_Online_Advertisemet_System/backend
```

**2. Install dependencies and set up the environment**

```sh
composer install
cp .env.example .env
php artisan key:generate
```

In `.env`, set your `DB_*` values for a database you have created. Add any credentials required by the application's configured authentication, mail, payment, and AWS S3 integrations. Keep credentials out of version control.

**3. Create the tables and start the API**

```sh
php artisan migrate --seed
php artisan serve --port=8008
```

The API will be available at `http://127.0.0.1:8008`. Start the [frontend](../frontend/README.md) separately on port `8000`.

> `.env` contains local settings and secrets. Create it from `.env.example`; do not commit it. Seed data and external integrations may require additional project-specific configuration.

## API endpoints

The main README lists these routes as examples of the API surface. Check `routes/api.php` for the complete route list and current request formats.

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/login` | Log in |
| POST | `/api/register` | Register an account |
| POST | `/api/logout` | Log out |
| POST | `/api/ads/create` | Create an ad |
| GET | `/api/ads` | Get live ads |
| DELETE | `/api/ads/{id}` | Delete an ad |
| GET | `/api/admin/getTodaysPaidAds` | Get today's paid ads |
| GET | `/api/admin/filterAds` | Filter ads in the admin dashboard |

## Technologies

Laravel and MySQL, with AWS S3 for ad images and API endpoints consumed by the frontend. Authentication and payment integrations support the corresponding user workflows.

## The team

This app was built by Ishari Abesooriya, Pasan Athuluwage, Wethma Sithumini, Ashini Hasara, and Basuru Jithmal. See the [main README](../README.md#the-team) for roles and profile links.

Thanks to **Nemo Technologies (Pvt) Ltd** for collaborating with us on the project.
