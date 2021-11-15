=================================================
Connect an Worldline Payment Terminal to your PoS
=================================================

Connecting a payment terminal allows you to offer a fluid payment flow
to your customers and ease the work of your cashiers.

Please note that Worldline is currently only available for customers in the
Belgium.

Configuration
=============

Some information for the Yomani Worldline BENELUX
-------------------------------------------------

- Default Technician password : 1235789
- If there is a cashier and customer terminal, configuration should be done on the cashier one
- Worldline assistance technique : 02 727 61 11 (“commercant” puis “assistance technique”)
- Check the initial configuration in case if issues in order to avoid to block the terminal
- You should set a fix IP to the IoT Box on the customer’s router in order to be sure the connexion won’t be lost 

Connect an IoT Box
------------------

Connecting an Worldline Payment Terminal to Odoo is a feature that
requires an IoT Box. For more information on how to connect an IoT Box
to your database, please refer to the :doc:`IoT connect </applications/productivity/iot/config/connect>`.

Configure the protocol
----------------------

Push on the `.` button of the terminal, then
:menuselection:`3 --> stop --> 3 --> 0 --> 9 --> Technician password --> 4 --> 2`

Push “MODIFIER” and choose CTEP for the “PROTOCOLE ECR”. `OK`.
Then press directly again `OK` (physical button) on three next screens “CTEP TICKET CAISSE”, “LARGEUR TICKET CAISSE”, and “JEU DE CARACTERES ISO”

:menuselection:`STOP --> STOP --> STOP` and then it will automatically restart

Set the IP address
------------------

Push on the `.` button of the terminal, then
:menuselection:`3 --> stop --> 3 --> 0 --> 9 --> Technician password --> 4 --> 9`

Click “MODIFIER” and choose TCP/IP for “CONFIGURATION CAISSE”. `OK`.
Click again `OK` on the next screen “TCP CONFIGURATION CLIENT”. 
And now the tricky part (one screen is one sequence of the IP address of the IoT Box that you can find in the IoT Box app in the customer’s database)

.. image:: media/worldline004.png
   :align: center

For “NOM DE L’HOTE”, type “10” > `OK` > Type “30” > `OK` > Type “19” > `OK` > Type “4” > `OK` > (leave empty) > `OK`

For “NUMERO DE PORT”, enter “9001” > `OK`
“PROTOCOLE ECR SSL NON” > `OK`

:menuselection:`STOP --> STOP --> STOP` and then it will automatically restart

Configure the payment method
----------------------------

First, go in the general settings of the POS app, and activate the
Worldline setting.

.. image:: media/worldline001.png
   :align: center

Go back in :menuselection:`Point of Sale --> Configuration --> Payment methods`.
Create a new payment method for Worldline, select the payment terminal option Worldline, and
select your payment terminal device.

.. image:: media/worldline002.png
   :align: center

Pay with a payment terminal
===========================

In your *PoS interface*, when processing a payment, select a *Payment
Method* using a payment terminal. Check that the amount in the tendered
column is the one that has to be sent to the payment terminal and click
on *Send*. When the payment is successful, the status will change to
*Payment Successful*.

.. image:: media/worldline003.png
   :align: center

If you want to cancel the payment request, click on cancel. You can
still retry to send the payment request.

If there is any issue with the payment terminal, you can still force the
payment using the *Force Done*. This will allow you to validate the
order in Odoo even if the connection between the terminal and Odoo has
issues.

.. note::
   This option will only be available if you received an error message
   telling you the connection failed.

Once your payment is processed, on the payment record, you’ll find the
type of card that has been used and the transaction ID.
