# GOAL

This is a demo to show-case how to geocode with no `address` but with street, city, zip and country as individual columns.

This demo was created from [this other one](https://github.com/andrerferrer/geocoder-gem#goal)

[You can also check my other demos](https://github.com/andrerferrer/dedemos/blob/master/README.md#ded%C3%A9mos).

## What needs to be done?

### 1. Add the gem
```ruby
# Gemfile
gem 'geocoder'
```

Remember to `bundle install`.

### 1. Add the latitude and longitude to the model

`rails g migration AddCoordinatesToModel latitude:float longitude:float`

Run the migration

`rails db:migrate`

### 1. Add `geocoder` to the model

```ruby
  # In the model
  geocoded_by :address
  after_validation :geocode, if: :will_save_change_to_address?
```


And we're good to go 🤓

Good Luck and Have Fun
