Delete Emails
^^^^^^^^^^^^^

The example below demonstrates how to delete an Email Resource in the
ThreatConnect platform:

.. code-block:: python
    :emphasize-lines: 12-15,18-19

    # replace the line below with the standard, TC script heading described here:
    # https://docs.threatconnect.com/en/latest/python/quick_start.html#standard-script-heading
    ...

    tc = ThreatConnect(api_access_id, api_secret_key, api_default_org, api_base_url)

    # instantiate Emails object
    emails = tc.emails()

    owner = 'Example Community'

    # create an empty Email
    email = emails.add('', owner)
    # set the ID of the new Email to the ID of the Email you would like to delete
    email.set_id(123456)

    try:
        # delete the Email
        email.delete()
    except RuntimeError as e:
        print(e)
        sys.exit(1)

.. note:: In the prior example, no API calls are made until the ``delete()`` method is invoked.
