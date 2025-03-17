# Djaport (Reports for tests in Django)


A package that will allow you to generate test reports of the tests that you have added in Django project.


You can track test by simply adding the following annotation in your test file:
```python
    @tag('<tag-name>')
    @djaport_test(
        category='<test-category>',
        author='<author-name>',
        description='<description>'
    )
```

Extend the Mixin in your testclass like following 
```python
class SomeUpdateAPITest(DjaportTestMixin, APITestCase):
    """
    Test cases for the update API endpoints
    """
```

and then 

You also need to initialize the mixin in your test class like following:

```python


def setUp(self):
        """
        Set up test data before each test
        """
        super().setUp()

```


and run your test like:

```shell
python manage.py test --testrunner=djaport.runner.CustomTestRunner
```
