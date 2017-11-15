# geocoder

First,to prevent API keys from public

```
gem 'figaro'

```
then

```
bundle exec figaro install

```

This creates a commented config/application.yml file and adds it to your .gitignore. Add your own configuration to this file and you're done!

Figaro may not need at this stage.

1- Now geocoder:

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

6- to put a map, choose the static map from:

```
Google Maps API Family - Google Code

```
Or we can add this in to : views>show

```
<%=image_tag "https://maps.googleapis.com/maps/api/staticmap?zoom=11&size=600x500
&markers=#{@location.latitude}%2c#{@location.longitude}" %>

```
