# CinemaPress

CinemaPress is an open-source CMS for building movie and TV show streaming portals. It's a Node.js/Express application using EJS templates, MySQL, and Sphinx Search.

## Project Structure

- `app.js` - Main application entry point
- `routes/` - Express route handlers (website, api, admin, player, etc.)
- `lib/` - Core library modules (cache, movies, sphinx search, etc.)
- `modules/` - Feature modules (api, player integrations, etc.)
- `themes/default/` - Default theme with EJS views and public assets
- `config/production/` - Active production configuration (generated)
- `config/locales/en/default/` - Default English locale configuration template
- `config/update/` - Config update scripts

## Configuration

Production config files are generated in `config/production/`:
- `config.js` - Main app configuration (domain, database, URLs, etc.)
- `modules.js` - Module configuration (comments, player, etc.)
- `config.backup.js` / `modules.backup.js` - Fallback configs

These were initialized from `config/locales/en/default/` on first setup.

## Dependencies

- **Express** - Web framework
- **EJS** - Template engine
- **MySQL** - Primary database
- **Sphinx Search** - Full-text search engine (`sphinx` npm package)
- **Maxmind** - GeoIP lookups (requires GeoLite2 database files)
- **pm2** - Process management

## Running

The app runs on PORT 5000 via the "Start application" workflow:
```
PORT=5000 node app.js
```

## Notes

- The homepage shows a 404 by default on a fresh install because it requires a MySQL + Sphinx Search database setup
- GeoLite2 database files (`GeoLite2-Country.mmdb`, `GeoLite2-ASN.mmdb`) go in the `files/` directory for IP geolocation
- Admin panel is available at `/admin-secret` (configurable in config)
