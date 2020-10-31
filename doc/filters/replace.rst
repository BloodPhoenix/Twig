``replace``
===========

The ``replace`` filter formats a given string by replacing the placeholders
(placeholders are free-form):

.. code-block:: twig

    {{ "I like %this% and %that%."|replace({'%this%': foo, '%that%': "bar"}) }}

    {# outputs I like foo and bar
       if the foo parameter equals to the foo string. #}

    {# using % as a delimiter is purely conventional and optional #}

    {{ "I like this and --that--."|replace({'this': foo, '--that--': "bar"}) }}

    {# outputs I like foo and bar #}

The placeholder can be stored in a variable. It must then be surrounded by parentheses:

.. code-block:: twig

    {% set twig_content_variable= 'Testing to replace content'%}
    {% set replace_value_var= 'Testing' %}
    {% set replace_with_value_var = 'Testing complete' %} 

    {{ twig_content_variable|replace({(replace_value_var): replace_with_value_var}) }}

    {# outputs Testing complete to replace content #}

Arguments
---------

* ``from``: The placeholder values

.. seealso:: :doc:`format<format>`
