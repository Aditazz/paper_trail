# Contributing

Thanks for your interest in PaperTrail!

Ask usage questions on Stack Overflow:
http://stackoverflow.com/tags/papertrail

**Please do not use github issues to ask usage questions.**

On github, we appreciate bug reports, feature
suggestions, and especially pull requests.

Thanks, and happy (paper) trails :)

## Development

Testing is a little awkward because the test suite:

1. contains a rails app with three databases (test, foo, and bar)
1. supports three different RDBMS': sqlite, mysql, and postgres

Run tests with sqlite:

```
# Create the appropriate database config. file
rm test/dummy/config/database.yml
DB=sqlite bundle exec rake prepare

# If this is the first test run ever, create databases
cd test/dummy
RAILS_ENV=test bundle exec rake db:setup
RAILS_ENV=foo bundle exec rake db:setup
RAILS_ENV=bar bundle exec rake db:setup
cd ../..

# Run tests
DB=sqlite bundle exec rake
```

Run tests with mysql:

```
# Create the appropriate database config. file
rm test/dummy/config/database.yml
DB=mysql bundle exec rake prepare

# If this is the first test run ever, create databases
cd test/dummy
RAILS_ENV=test bundle exec rake db:setup
RAILS_ENV=foo bundle exec rake db:setup
RAILS_ENV=bar bundle exec rake db:setup
cd ../..

# Run tests
DB=mysql bundle exec rake
```
