## gitlab-rails console
### Unblock user

=== "Command"

    ```bash
    gitlab-rails console -e production
    user = User.find_by(email: 'johndoes@example.com')
    user.state="active"
    user.save
    ```

