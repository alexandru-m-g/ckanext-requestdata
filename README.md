## Request data &middot; [![Build Status](https://travis-ci.org/ViderumGlobal/ckanext-requestdata.svg?branch=master)](https://travis-ci.org/ViderumGlobal/ckanext-requestdata)

These extension allow users to publish  dataset metadata without
uploading any file(s). The owner
of the dataset, as well as the admins of the organization that the dataset
belongs to can take actions on these requests and decide what to share.

## Full Documentation
See our [Wiki](https://github.com/ViderumGlobal/ckanext-requestdata/wiki) for full documentation, examples, operational details and other information.

## Installation

To install ckanext-requestdata:

1. Activate your CKAN virtual environment, for example:

     . /usr/lib/ckan/default/bin/activate

2. Install the ckanext-requestdata Python package into your virtual environment:

     pip install ckanext-requestdata

3. Add ``requestdata`` to the ``ckan.plugins`` setting in your CKAN
   config file (by default the config file is located at
   ``/etc/ckan/default/production.ini``).

4. Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu:

     sudo service apache2 reload


## Config Settings

These are the required configuration options used by the extension:
```
hdx_portal = False
smtp.server=YOUR_SMTP_SERVER
smtp.user=YOUR_SMTP_USERNAME
smtp.password=YOUR_SMTP_PASSWORD
smtp.mail_from =SENDER_MAIL
```

You can add these additional options in the config for footer links in the email
when new data request is sent:
```
ckanext.requestdata.newsletter_url
ckanext.requestdata.twitter_url
ckanext.requestdata.contact_email
```

## Development Installation

To install ckanext-requestdata for development, activate your CKAN virtualenv
and do:

```
git clone https://github.com/ViderumGlobal/ckanext-requestdata.git
cd ckanext-requestdata
python setup.py develop
pip install -r dev-requirements.txt
```

## Running the Tests

To run the tests, first make sure that you have installed the required
development dependencies in CKAN, which can be done by running the following
command in the CKAN's `src` directory:

```
pip install -r dev-requirements.txt
```

After that just type this command to actually run the tests in the extension.

```
nosetests --ckan --with-pylons=test.ini
```
To run the tests and produce a coverage report, first make sure you have coverage installed in your virtualenv (pip install coverage) then run:

```
nosetests --nologcapture --with-pylons=test.ini --with-coverage --cover-package=ckanext.requestdata --cover-inclusive --cover-erase --cover-tests
```
