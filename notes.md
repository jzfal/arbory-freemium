# Design doc for free tier of arbory

To create the site run `django-admin startproject arbory`
To create the app run `django-admin startapp account`
To migrate the new app to the site database run `python manage.py migrate`

## Authentication framework 
* User: A user model with basic fields; the main fields of this model are username, password, email, first_name, last_name, and is_active 
* Group: A group model to categorize users 
* Permission: Flags for users or groups to perform certain actions 

To create super user run `python manage.py createsuperuser`

The registration in templates is the default path for the Django authentication views (django expects them to be here)

for the urls module under the application, the given 'name' can be used in href in out templates to redirect 

The hidden HTML `<input>` element submits the value of a varible called next. This variable is first set by the login view when you pass a next params in the request(for example, http:root/account/login/?next=/account/). The next param has to be a URL. If this param is given, the django login view will redirect the user to the given URL after a successful login. 

T