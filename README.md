# i18n_generators

A Rails plugin that generates the I18n locale files with automatic
translation. Supporting Rails 5.1, 5.0, 4.2.x, 4.1.x, 4.0.x, 3.2.x, 3.1.x, 3.0.x,
2.3.x, and 2.2.x.

Here's an example of generating a translation file (the example model is taken
from [the Rails Girls app](http://guides.railsgirls.com/app/#create-idea-scaffold)).

    % rails g scaffold idea name description:text picture
    % rails g i18n ja

![translation_ja.yml](https://raw.githubusercontent.com/amatsuda/i18n_generators/414e923ae1a6450f0005b486376d084a88938a9e/assets/i18n_ja_example.png)

## Features

This gem/plugin provides following three generator commands.

### 1. Generate Locale Files for ActiveRecord/ActiveSupport/ActionPack/ActionView

    % rails g i18n_locale ja (de-AT, pt-BR, etc.)

Downloads the .yml file for the specified locale from the official rails-i18n
repository:
    https://github.com/svenfuchs/rails-i18n/tree/master/rails/locale

Then the generator sets the application default locale to the specified
locale.

This will generate following locale file.

    config/locales/ja.yml

### 2. Generate Translation YAML File For All Models/Attributes

    % rails g i18n_translation ja (de-AT, pt-BR, etc.)

This will generate following YAML file.

    config/locales/translation.ja.yml

The generator scans your app/models directory, and generates a YAML file with
all the AR model names and attributes so that you don't have to write the YAML
skeleton manually. In addition, the generator tries to translate each of them
into the specified language. The generator doesn't overwrite the existing
value so that you can rerun the generator again and again.

The #g mark in the generated YAML means that the line is generated by the
generator.

### 3. Generate All

    % rails g i18n ja (de-AT, pt-BR, etc.)

Executes 1 and 2 at once.


## Supported versions

*   Ruby 2.3, 2.2.x, 2.1.x, 2.0.0, 1.9.x, 1.8.7
*   Ruby on Rails 5.1, 5.0, 4.2, 4.1, 4.0, 3.2, 3.1, 3.0
*   Ruby on Rails 2.3, 2.2 (supported by i18n_generators < 1.2)


## Installation

*   Rails 3 or higher (with Bundler)


Add 'i18n_generators' to your Gemfile, then `bundle`. Restricting the group to
:development would be a good idea, since the generator would probably be used
only in development mode.

*   Rails 2


Use 'i18n_generators' version '< 1.2'.


## Copyright

Copyright (c) 2008 Akira Matsuda, released under the MIT license
