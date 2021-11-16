========
Buckaroo
========

`Buckaroo <https://www.buckaroo.eu/>`_ is a Dutch-based company that offers several online payment
possibilities.

Configuration
=============

.. seealso::
   - :ref:`payment_acquirers/add_new`

Credentials tab
---------------

Odoo needs your **API Credentials** to connect with your Buckaroo account, which comprise:

- :ref:`Website Key <buckaroo/website_key>`: The key solely used to identify the website with
  Buckaroo.
- :ref:`Secret Key <buckaroo/secret_key>`: The secret key you entered on Buckaroo.
- :ref:`Push response URLs <buckaroo/push_response>`: The push response URLs you entered on Buckaroo.

You can copy your credentials from your Buckaroo account, and paste them in the related fields under
the **Credentials** tab.

.. _buckaroo/website_key:

Website Key
~~~~~~~~~~~

In order to retrieve the Website Key, log into your Buckaroo account, go to
:menuselection:`Configuration --> Templates --> Your Website`.

.. _buckaroo/secret_key:

Secret Key
~~~~~~~~~~

In order to retrieve the Website Key, log into your Buckaroo account, go to
:menuselection:`Configuration --> Security --> Secret Key`.

.. important::
   If you are trying Buckaroo in a test account, change the **State** to *Test Mode*. We
   recommend doing this on a test Odoo database, rather than on your main database.

.. seealso::
   - :doc:`../payment_acquirers`

.. _buckaroo/push_response:

Push response URLs
~~~~~~~~~~~~~~~~~~

To retrieve the URLs, log into your Buckaroo account, go to
:menuselection:`My Buckaroo --> Websites --> Push settings`, and be sure to check in :menuselection:`Enable Push Response`.
Add your :menuselection:`Push URI Success` and your :menuselection:`Push URI Failure`. These two URLs should be finished by :menuselection:`/payment/buckaroo/webhook`.

You have to save the page to finalize the push response URLs creation.