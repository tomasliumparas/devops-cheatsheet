## Access

### Reset admin password
=== "sql"
    ```sql
    UPDATE wp_users SET user_pass = md5('new_password') WHERE user_login = 'admin';
    ```

=== "output"
    ```sql
    Rows matched: 1  Changed: 1  Warnings: 0
    ```
