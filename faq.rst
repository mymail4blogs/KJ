Frequently Asked Questions
==========================

How to create a new site ?
--------------------------------------

First, you should check out the Builds tab of your project. That records all of the build attempts that RTD has made to build your project. If you see ``ImportError`` messages for custom Python modules, you should enable the virtualenv feature in the Admin page of your project, which will install your project into a virtualenv, and allow you to specify a ``requirements.txt`` file for your project.

If you are still seeing errors because of C library dependencies, please see the below section about that.

How to create a new space ?
-------------------------------------------

When RTD builds your project, it sets the `READTHEDOCS` environment variable to the string `True`. So within your Sphinx's conf.py file, you can vary the behavior based on this. For example::

    import os
    on_rtd = os.environ.get('READTHEDOCS', None) == 'True'
    if on_rtd:
        html_theme = 'default'
    else:
        html_theme = 'nature'

The ``READTHEDOCS`` variable is also available in the Sphinx build environment, and will be set to ``True`` when building on RTD::

    {% if READTHEDOCS %}
    Woo
    {% endif %}

How to associate a resource with space ?
----------------------------------------------------------

.. note::
    This is the way we can add a new note



code snippet::

    

    public abstract class AbstractResourceTemplate implements ResourceTemplate {
    private Space<?> space;
    private PropertyTypeLoader propertyTypeLoader;
    private Function<List<PropertyType>, List<PropertyType>> staticPropertyFilter;
    
    protected AbstractResourceTemplate(){
    }
    
    public void setSpace(Space<?> space){
        this.space = space;
    }
    
    public void setPropertyTypeLoader(PropertyTypeLoader propertyTypeLoader){
        this.propertyTypeLoader = propertyTypeLoader;
    }
    
    
 }

    
How to create a new property?
----------------------------------------------------------

You can do this for Google at least with a canonical link tag.
It should look like:

.. code-block:: jinja

        <link rel="canonical" href="http://ericholscher.com/
        {%- for word in pagename.split('/') -%}
            {%- if word != 'index' -%}
                {%- if word != '' -%}
                    {{ word }}/
                {%- endif -%}
            {%- endif -%}
        {%- endfor -%}
        {% if builder == "dirhtml" %}/{% else %}.html{% endif %}
        ">


How to associate one property with space and resource
--------------------------------------------

RTD doesn't expose this in the UI, but it is possible to remove the build directory of your project. If you want to remove a build environment for your project, hit http://readthedocs.org/wipe/<project_slug>/<version_slug>/. You must be logged in to do this.


How to create a new category?
---------------------------------------------

We support the concept of Subprojects.
If you add a subproject to a project,
that documentation will also be served under the parent project's subdomain.

For example,
Kombu is a subproject of celery,
so you can access it on the `celery.readthedocs.org` domain:

http://celery.readthedocs.org/projects/kombu/en/latest/

This also works the same for CNAME's:

http://docs.celeryproject.org/projects/kombu/en/latest/

You can add subprojects in the Admin section for your project.

How to add a category to the property ?
--------------------------------------------------

Read the Docs will crawl your project looking for a ``conf.py``. Where it finds the ``conf.py``, it will run ``sphinx-build`` in that directory. So as long as you only have one set of sphinx documentation in your project, it should Just Work.

I want to use the Blue/Default Sphinx theme
-------------------------------------------

We think that our theme is badass, and better than the default for many reasons. Some people don't like change though :), so there is a hack that will let you keep using the default theme. If you set the ``html_style`` variable in your ``conf.py``, it should default to using the default theme. The value of this doesn't matter, and can be set to ``/default.css`` for default behavior.

How to check permission on space ?
---------------------------------------------

There is a repository for that: https://github.com/snide/sphinx_rtd_theme.
Simply follow the instructions in the README.

How to check permission on a resource ?
-----------------------------------------------

Image scaling in docutils depends on PIL. PIL is installed in the system that RTD runs on. However, if you are using the virtualenv building option, you will likely need to include PIL in your requirements for your project.

How to check permission on category ?
--------------------------

RTD doesn't have explicit support for this. That said, a tool like `Disqus`_ can be used for this purpose on RTD.

.. _Disqus: http://disqus.com/

How to add a space to a site?
-----------------------------------------------------

See the section on :ref:`Localization of Documentation`.

How to assign a role to a contact?
----------------------------

No. Whitelisting has been removed as a concept in Read the Docs. You should have access to all of the features already.


