## PgHero Heroku Standalone

Want to run the [PgHero engine](https://github.com/ankane/pghero/), but don't want to
add more dependencies to your existing Rails app? Then this little repo is for you!

This a standalone Rails 4.2 app which can be easily deployed to Heroku. Just point it at 
an existing Heroku database using `DATABASE_URL`.

## Requirements
I found it easiest to run this on Heroku's heroku-16 stack using Ruby 2.3.0.

## Install

```
git clone https://github.com/kyleschmolze/pghero-heroku-standalone
cd pghero-heroku-standalone
heroku create my-pghero-app
heroku stack:set heroku-16
heroku config:set PGHERO_USERNAME=your_username
heroku config:set PGHERO_PASSWORD=your_password
heroku config:set DATABASE_URL=database_url_of_existing_app
git push heroku master
```

If Heroku doesn't allow you to detach the `DATABASE_URL` before deleting the database itself, run:
```
```


## Test Locally
If you have a Postgres database running locally, you may:

1. Update `config/database.yml` to use your postgres database.

2.  `bundle install`

3. `rails server`

3. Open `localhost:3000`

Todo
- destroy database cmd line
