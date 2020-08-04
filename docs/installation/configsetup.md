---
title: Confugrations Setup
---

# Configuring Setup on Localhost

## Giving User Administrative Roles

In order to access the configurations panel, you must be logged with a user with
the `admin` role activated. You must also have the `single_resource_admin` role
in order to make changes to your configurations page.

To activate such a role, you can follow these instructions:

- open the Rails console

```shell
rails console
```

1. load the user object of for _joe_ (or whatever the username is)

```ruby
Loading development environment (Rails 5.2.3)
[1] pry(main)> user = User.find_by(username: "joe")
[2] pry(main)> user.add_role(:super_admin)
[3] pry(main)> user.add_role(:single_resource_admin)
[4] pry(main)> user.save!
```

This allows you to access the configurations page on your local setup. Once
there you can now read and edit the parameters included to setup your home page.

Using https://github.com/forem/forem/pull/8435 you can now input all the fields
required. Although not all fields do not need to be filled in, the mandetory
fields must be included. Once this is setup, the homepage can now be viewed
normally.
