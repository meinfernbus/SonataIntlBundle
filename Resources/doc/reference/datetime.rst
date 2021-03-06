Datetime Helper
================

The DateTime helper provides functions to format:

 - a date :  ``format_date``
 - time   : ``format_time``
 - date and time : ``format_datetime``

Twig usage
----------

You can format a compatible date with 4 methods, a date can be:

 - a ``DateTime`` object
 - a timestamp : ``375930000``
 - a date string : ``'1981-11-30'``


.. code-block:: jinja

    {{ date_time_object | format_date }} => '1 août 2011'
    {{ date_time_object | format_time }} => '19:55:26'
    {{ date_time_object | format_datetime }} => '1 août 2011 19:55:26'

By default the helpers methods use the current user's locale to display 
information. Of course this behavior can be controller from within the template 
by providing extra parameters :

* pattern : the pattern to use to render the date
* the locale
* the timezone to use if date is not a ``DateTime`` instance

.. code-block:: jinja

    {{ date_time_object | format_date(null, 'fr', 'Europe/Paris') }} => '1 août 2011'
    {{ date_time_object | format_time(null, 'fr', 'Europe/Paris') }} => '19:55:26'
    {{ date_time_object | format_datetime(null, 'fr', 'Europe/Paris') }} => '1 août 2011 19:55:26'
    {{ date_time_object | format_[date|time|datetime]('dd MMM Y G', 'fr', 'Europe/Paris') }} => '01 août 2011 ap. J.-C.'


.. note::

    More information about patterns can be found here: 
    http://userguide.icu-project.org/formatparse/datetime
