# Go for it! 100% Ruby

## To all Rubyists that hate Javascript

![Repository Languages](images/01_repository_languages.png)

by Kevin Fischer / @kfischer_okarin

---

## Kevin Fischer

![Avatar](images/02_avatar.jpg)
{: class="top-right" style="width: 25%"}

* Born and raised in Germany
* Christian, believing in and
  following Jesus Christ
* Programmer at Agileware since 2016
* Married since January

```note
クリスチャンです。つまり、イエス・クリストを信じて、ついていく人です。
```

---

![Game Screenshot](images/03_game_screenshot.png)
![Made with Unity](images/03_unity.png)

---

![Game Screenshot](images/04_spiderman.jpg)

```note
ニューヨークの街を飛び回ったりしています。
```

---

## Kaigress - Overview

![Network](images/05_kaigress.png)

---

## Kaigress - My Network

![Close-up](images/06_kaigress2.png)

---

## What I will talk about

* Rewriting the (small) frontend of Kaigress from Slim to Opal+Ferro
* My impression

---

## Adding gems

```ruby
# Gemfile

gem 'opal', '~> 0.11.4'
gem 'opal-rails'
gem 'opal-ferro', '~> 0.11.0'
```

---

## Adding gems

```ruby
# Gemfile

gem 'opal', '~> 0.11.4' <-------------------
gem 'opal-rails'
gem 'opal-ferro', '~> 0.11.0'
```

---

## Opal

https://github.com/opal/opal

![Opal](images/07_opal.png)

---

## Adding gems

```ruby
# Gemfile

gem 'opal', '~> 0.11.4' <-------------------
gem 'opal-rails'
gem 'opal-ferro', '~> 0.11.0'
```

---

## Adding gems

```ruby
# Gemfile

gem 'opal', '~> 0.11.4'
gem 'opal-rails' <--------------------------
gem 'opal-ferro', '~> 0.11.0'
```

---

## opal-rails - Sprockets

Adds a sprockets extension for js.rb files, so this

```js
// application.js

//= require rails-ujs
//= require opal
//= require turbolinks
//= require_tree .
```

---

## opal-rails - Sprockets

can be written like this and is automatically compiled to Javascript.

```ruby
# application.js.rb

require 'rails-ujs'
require 'opal'
require 'turbolinks'
require_tree '.'
```

---

## opal-rails - Opal Templates

```ruby
# app/views/users/_new.js.opal

class NewUserView
  # Fancy UI Framework stuff
end

NewUserView.new.render
```

---

## Adding gems

```ruby
# Gemfile

gem 'opal', '~> 0.11.4'
gem 'opal-rails' <--------------------------
gem 'opal-ferro', '~> 0.11.0'
```

---

## Adding gems

```ruby
# Gemfile

gem 'opal', '~> 0.11.4'
gem 'opal-rails'
gem 'opal-ferro', '~> 0.11.0' <-------------
```

---

## Ferro

https://github.com/easydatawarehousing/opal-ferro

```ruby
class Panel < Ferro::Component::Base
  def before_create
    @title = option_replace :title
    @content = option_replace :content
  end

  def cascade
    add_child :header, Header, content: @title if @title
    add_child :content, Body, content: @content
  end
end
```

---
