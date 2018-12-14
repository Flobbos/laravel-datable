# Laravel-Datable


![Laravel Databale](img/laravel-datable.png)

**For easy date localization**

If you have trouble working with localized date formats used in combination
with translations then this package might be for you. It simply provides a
trait that you can add to your models which use https://github.com/jenssegers/date
to provide localized date outputs. 


### Docs

* [Installation](#installation)
* [Usage](#usage)
* [Laravel compatibility](#laravel-compatibility)

## Installation

#### Install the package

```bash
composer require flobbos/laravel-datable
```
That's it. Nothing else to do at this point. 

## Usage

#### Add it to the model

```php

    namespace App;

    use Illuminate\Database\Eloquent\Model;
    use Flobbos\Datable;

    class Event extends Model {

        use Datable\Datable;

        protected $dates = [
            'starts_on',
            'ends_on'
        ];


    }
```
This is all you need to do to make it work. You won't notice a difference anywhere
except when you're pulling formats like this:

```php
    $your_model->starts_on->format('d. F Y');
```

The output will then have the localized month name instead of the default English. 
