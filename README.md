# FindIt - Buy, Sell, Discover

**FindIt** is a web platform where people can post classified ads, and admins can manage and filter everything from a dashboard. Ads can be filtered by district, town, price range, and category.

Built with Laravel on both sides — the backend runs as an API, and the frontend consumes it. This was our second-year industry-level project, done with a real client.

## About the project

We approached **Nemo Technologies (Pvt) Ltd** looking for a real project to work on, and they assigned us this one. We built it as a team and handed it over to them when it was finished.

## What it does

**For users**
- Sign in with Google, Facebook, mobile OTP, or plain email and password
- Post free or paid ads with images and full details
- Filter ads by location, price, and category

**For admins**
- View, edit, and delete user accounts
- Approve, reject, or remove ads
- Search and filter ads dynamically

**Under the hood**
- Images stored on AWS S3
- API-driven setup, so the frontend and backend stay cleanly separated

## Project structure

The repo is split into two Laravel applications.

### `backend/` - the API

Handles authentication, ad management, and all the filtering logic.

| Folder | What's in it |
|---|---|
| `app/` | Controllers, models, middleware - the core logic |
| `config/` | Config for mail, database, sessions, and so on |
| `database/` | Migrations, factories, seeders |
| `public/` | Entry point (`index.php`) and public assets |
| `resources/` | Blade views for the admin templates |
| `routes/` | API and web route definitions |
| `storage/` | Cache, logs, uploaded files |
| `tests/` | Unit and feature tests |

### `frontend/` — the user interface

Laravel Blade, Bootstrap, and AJAX. Talks to the backend API.

| Folder | What's in it |
|---|---|
| `app/` | Frontend controllers and models |
| `config/` | Session, view, and other frontend config |
| `public/` | Images, CSS, JavaScript |
| `resources/` | Blade templates and SCSS |
| `routes/` | Web routes |
| `tests/` | Feature and unit tests |

## Getting it running

**1. Clone it**

```sh
git clone https://github.com/Ishari-928/FindIT_Online_Advertisemet_System.git
cd FindIT_Online_Advertisemet_System
```

**2. Backend**

```sh
cd backend
composer install
cp .env.example .env
php artisan key:generate
```

Open `.env` and fill in your database credentials and AWS S3 keys. Then:

```sh
php artisan migrate --seed
php artisan serve --port=8008
```

**3. Frontend**

In a new terminal:

```sh
cd frontend
composer install
cp .env.example .env
php artisan key:generate
npm install
npm run dev
```

And in another terminal:

```sh
php artisan serve
```

> Note: `.env` files aren't committed to this repo - they hold secrets. Copy `.env.example` and fill in your own values.

## API endpoints

**Authentication**

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/login` | Log in |
| POST | `/api/register` | Register a new account |
| POST | `/api/logout` | Log out |

**Admin**

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/admin/getTodaysPaidAds` | Today's paid ads and what's next |
| GET | `/api/admin/filterAds` | Filter by district, town, category, price |

**Ads**

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/ads/create` | Post a new ad |
| GET | `/api/ads` | Get all live ads |
| DELETE | `/api/ads/{id}` | Delete an ad |

## The team

This was a group project. Everyone below worked on it:

| Name | Role |
| [Pasan Athuluwage](https://github.com/MinjanaAP) | Project Manager & Full Stack Developer |
| [Ishari Abesooriya](https://github.com/Ishari-928) | Business Analyst & Full Stack Developer |
| [Wethma Sithumini](https://github.com/wethmasithumini) | Full Stack Developer |
| [Ashini Hasara](https://github.com/ashinihasara) | Full Stack Developer |

### My contribution

I worked on this in two roles - Business Analyst and full-stack developer.

**As Business Analyst**

I was the main point of contact between the team, our supervisors, and the client at Nemo Technologies. That meant sitting in on requirement discussions, working out what the client actually needed, and turning that into something the team could build from — project scope, user stories, and acceptance criteria.

I also wrote and maintained the project's SRS document, covering the functional and non-functional requirements across all eleven ad categories, the admin and super-admin role definitions, the reporting system, and the paid advertisement rules.

Tools: Figma for translating requirements into interface designs, Jira for tracking work, Bitbucket for version control during development.

**As a developer**

I owned these features end to end - frontend, backend API, and the admin panel side of each:

- **Paid advertisement module** - create, edit, and delete paid ads, including the payment gateway integration
- **Ad deletion** - the delete flow across all advertisement types
- **Favourites** - letting users save ads to a favourites list
- **Ratings** - adding and removing ratings on advertisements
- **Social sharing** - share buttons letting users post an ad straight to WhatsApp or Facebook

Built with Laravel and Bootstrap on the frontend, Laravel API on the backend.

Thanks to **Nemo Technologies (Pvt) Ltd** for the collaboration and support throughout.

## License

MIT.

## Contact

Happy to talk about the project or anything related.

📧 ishariabeysooriya928@gmail.com
👩‍💻 [github.com/Ishari-928](https://github.com/Ishari-928)