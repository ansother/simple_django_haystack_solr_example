simple_django_haystack_solr_example
======================================

About
----------

:date: 2012/07/07

This is a simple django-haystack example that uses solr as the back end. Solr setup is not covered in this project.

Requirements
--------------

Setup was on ubuntu

    Django==1.4
    django-haystack==2.0.0-beta
    pysolr==2.1.0-beta

Additionally you need to setup solr. I used this tutorial: http://charlesleifer.com/blog/solr-ubuntu-revisited/

Installation and setup
---------------

1. Download and move into the simple_django_haystack_solr_example
    
    $ cd simple_django_haystack_solr_example/

2. Install requirements from the r.txt file with pip:

    $ pip install -r r.txt
    
3. Setup database:
    
    $ python manage.py sncdb
    
4. Run the Django development server:
    
    $ python manage.py runserver 0.0.0.0:8000
    
5. Go to the admin panel -> notes app and create test data:

    http://localhost:8000/admin
    
6. Copy the solr schema.xml and stopwords_en.txt to solr config folder (usually solr/solr/conf)

    $ sudo cp schema.xml stopwords_en.txt /path/to/solr/configuration/directory
    
7. Start solr server:
    
    $ sudo java -jar start.jar
    
8. Build solr index:

    $ python manage.py rebuild_index
    
9. Run the Django development server:

    $ python manage.py runserver 0.0.0.0:8000

10. Go to search page:

    http://localhost:8000/search



