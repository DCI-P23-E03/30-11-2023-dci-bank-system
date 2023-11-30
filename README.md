# 30-11-2023-dci-bank-system
## Title:
Atomicity
## Estimated Time:
9 h
## Difficulty Level:
Intermediate
## Prerequisites:
4.5 Framework - Forms
## Tοpics covered
- django ORM
- django forms
- django templating
- class based views
- Testing (after the test module)
## Scenario
The goal of this exercise is to create a simple banking application using Django that supports the transfer of money from one customer to another. This exercise covers several important concepts in Django such as models, forms, views, templates, and database transactions.\

In this exercise, you will design a simple banking application in Django that allows users to transfer money between accounts. Here are the steps you should follow:

1. Create a new Django project called `banking_project` by running `django-admin startproject banking_project`.

2. Create a new Django app called `banking` by running `python manage.py startapp banking`.

3. Define a `Customer` model in the `models.py` file of the `banking` app. The `Customer` model should have the following fields:

   * `name` (CharField)
   * `bank_number` (CharField)
   * `balance` (IntegerField)
   * `joining_date` (DateTimeField)

   Use the `auto_now_add` attribute for `joining_date` so that it is automatically set when a new `Customer` object is created.

4. Register the `Customer` model with the admin site by creating a new `admin.py` file in the `banking` app and registering the `Customer` model.

5. Create two Django forms in the `forms.py` file of the `banking` app:

   * A `CustomerForm` form that allows users to create a new `Customer` object. The form should have fields for `name`, `bank_number`, and `balance`. Use the Django form API to create this form.

   * A `TransferForm` form that allows users to transfer money from one `Customer` object to another. The form should have fields for `sender`, `recipient`, and `amount`. Use the Django form API to create this form.

6. Create a Django view in the `views.py` file of the `banking` app that displays a list of all `Customer` objects along with their `bank_number` and `balance`. Use class-based views for this.

7. Create a Django view in the `views.py` file of the `banking` app that handles transfers between `Customer` objects. Use the `transaction.atomic` decorator to ensure that the transfer is completed atomically. If the transfer is successful, redirect the user to a success page. If the transfer fails due to insufficient funds, display an error message.

8. Create a Django template called `base.html` in the `templates` directory of the project. This template should contain the basic HTML structure for all pages in the application. Use the Django template language to define blocks for the page title, page content, and any scripts or stylesheets that should be included.

9. Extend the `base.html` template to create templates for the following pages:

   * A template for the customer list view that displays a table of all customers with their bank number and balance.
   * A template for the customer form view that displays a form for creating a new customer.
   * A template for the transfer form view that displays a form for transferring money between customers.
   * A template for the success page that displays a message confirming that the transfer was successful.

10. Define URL patterns for each of the views in the `urls.py` file of the `banking` app. Use the `name` attribute to name each URL pattern. The URL patterns should map to the appropriate view functions.

11. Include the `banking` app's URL patterns in the project's `urls.py` file using the `include()` function.

12. Run the Django development server using `python manage.py runserver` and test the application in a web browser. Verify that you can create new `Customer` objects, transfer money between accounts, and view a list of all customers with their bank number and balance.
