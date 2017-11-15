# geocoder

1-

```
gem 'geocoder'

```
2- A collection of useful Rails generator scripts for scaffolding, layout files, authentication, and more.

```
gem "nifty-generators"

```
3- creating a model called location and then rake db:migrate

```
rails g scaffold location address:string latitude:float longitude:float

```

4- in models>location.rb

```
geocoded_by :address
after_validation :geocode, :if => :address_changed?

```

5- in url and location field if enter an address it will return Longitude and latitude.
