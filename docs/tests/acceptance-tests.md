---
sidebar_position: 1
---

# Acceptance Tests

Acceptance tests are tests from the perspective of the end-user.

In the Rails world, we sometimes refer to these as Feature or System tests. A
tool called Capybara is included to help us simulate a human's actions inside of
our tests.

Generally, we are simulating what a user could do from their web browser and
ensuring that the app behaves as intended. When a feature is heavily reliant on
interaction from a user via the browser, it's a good idea to write automated
Acceptance tests to uncover any bugs that might not be apparent from manual
testing.

It's important to note that Rails System tests can be fairly slow, so it's
better to focus on testing core functionality or pieces of your code that you
think might be prone to regressions. Another strategy we use to help us keep
acceptance tests fast is `:aggregate_failures`. `:aggregate_failures` allows us
to make multiple assertions within a single test. The flag signals to Rspec to
run each assertion and then report all of the failures back to us rather than
just the first failure. This saves time because we only have to setup the
conditions for the spec once and then make all of our assertions instead of
setting up the conditions repeatedly for each individual assertion.

Acceptance tests can be found in the directory `spec/system`.

You can run all acceptance tests with:

```shell
bundle exec rspec spec/system
```

To run an individual file you can use:

```shell
bundle exec rspec spec/system/user_views_a_reading_list_spec.rb
```

To run a specific test case you can use:

```shell
bundle exec rspec spec/system/user_views_a_reading_list_spec.rb:10
```

where `10` is the line number of the test case that you want to execute.

You can read the official guide
[Testing Rails Applications](https://guides.rubyonrails.org/testing.html#system-testing)
to learn more.
