## To setup and run locally:
bundle install
bundle exec middleman server

Now you can see the docs at http://localhost:4567


## To deploy:
./deploy.sh

## NB:
Make sure the gh-pages branch is active in the GitHub Pages section at https://github.com/OnboardFlow/api-docs/settings

## Common errors:
Make sure Gemfile.lock is not modified. Seems that is the original list of package version numbers that we need to install.
