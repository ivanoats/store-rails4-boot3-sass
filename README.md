# Twitter Bootstrap Basics with Rails 4, Bootstrap 3, and SASS

I attempted to do Ryan Bates' Twitter Bootstrap Basics, but it's a bit out of date.
Here are my updates and way I got it done.

- rails new store --skip-test-unit
- cd store
- rails g scaffold product name price:decimal --skip-stylesheets
- rake db:migrate
- put `gem 'bootstrap-sass', github: 'thomas-mcdonald/bootstrap-sass'` in your Gemfile
- bundle install
- put `//= require bootstrap` in your app/assets/javascript/application.js file
- make a file in app/assets/stylesheets called `load_bootstrap.css.scss` and in that file put:

```scss
@import "bootstrap";
```

- in app/assets/stylesheets/application.css should look something like this:

```
 *= require_self
 *= require load_bootstrap
 *= require_tree .
 */
```

This loads the load_bootstrap file into the asset pipeline.

- wrap a `<div class="container">` around the yield in app/views/layouts/application.html.erb
- you'll see a bit better formatting
- then in general you can continue on with some of the suggestions from the railscast, but
for any css classes you may have to update them to Bootstrap v3. Check out http://getbootstrap.com/getting-started/#migration

