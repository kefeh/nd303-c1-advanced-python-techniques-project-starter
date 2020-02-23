## Task 3 Bugs, Errors and Fixes

After running the tests, some tests failed. Below are the tests and their fixes

- ERROR: test_find_unique_number_between_dates_with_diameter (tests.test_neo_database.TestNEOSearchUseCases)
AttributeError: 'NearEarthObject' object has no attribute 'diameter_min_km'

So I had to go and rename an attribute, `estimated_diameter_min_kilometers`, in NearEarthObject model to `diameter_min_km`

That fixed the error.

Another error was:
- ERROR: test_find_unique_number_between_dates_with_diameter_and_hazardous_and_distance (tests.test_neo_database.TestNEOSearchUseCases)

AttributeError: 'OrbitPath' object has no attribute 'neo_name'

So I had to rename an attribute `name` in OrbitPath to `neo_name`

That fixed that error as well.

Another test was failing
- FAIL: test_find_unique_number_neos_on_date_with_diameter (tests.test_neo_database.TestNEOSearchUseCases)

AssertionError: 10 != 4

It probably was an error with my search implementation

I had not changed the `estimated_diameter_min_kilometers` to `diameter_min_km` in my Filter.Options. So I did the change and then the test passed.