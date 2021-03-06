Django Tagging Translated
=========================

Registers the ``Tag`` model of
`django-tagging <https://github.com/brosner/django-tagging>`_ for
`simple-translation <https://github.com/fivethreeo/simple-translation>`_ and
extends the Tag admin.


Installation
------------

Prerequisites:

* Django
* django-tagging
* simple-translation

If you want to install the latest stable release from PyPi::

    $ pip install django-tagging-translated

If you feel adventurous and want to install the latest commit from GitHub::

    $ pip install -e git://github.com/bitmazk/django-tagging-translated.git#egg=tagging_translated

Add ``tagging_translated`` to your ``INSTALLED_APPS``::

    INSTALLED_APPS = (
        ...,
        'tagging_translated',
    )

Run the South migrations::

    ./manage.py migrate tagging_translated


Usage
-----

When you create tags, for example via the Entry admin of cmsplugin-blog,
the english translation will be generated automatically. You can use it in
your templates like so::

    {% load i18n simple_translation_tags %}

    {% with tag|get_preferred_translation_from_request:request as tag_title %}
    <p>{{ tag_title.trans_name }}</p>
    {% endwith %}


Roadmap
-------

Check the issue tracker on github for milestones and features to come.
