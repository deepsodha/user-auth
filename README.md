# SQLX CLI
cargo install sqlx-cli

# Run migrations
sqlx mig run

# Run the server (http://localhost:3000)
cargo run
```

### API
- Health endpoint: `GET` /
  ```
  curl http://localhost:3000/
  ```
- User Signup: `POST` /signup
  ```
  curl --request POST \
    --url http://localhost:3000/signup \
    --header 'content-type: application/json' \
    --data '{
        "username": "user1",
        "email": "user1@example.com",
        "password": "user1"
    }'
  ```
- Auth: `POST` /auth
  ```
  curl --request POST \
    --url http://localhost:3000/auth \
    --user user1
  ```
- User profile: `GET` /me
  ```
  curl --request GET \
  --url http://localhost:3000/me \
  --header 'authorization: Bearer <jwt_token>'
  ```
- Update profile: `PUT` /me
  ```
  curl --request POST \
    --url http://localhost:3000/me \
    --header 'authorization: Bearer <jwt_token>' \
    --header 'content-type: application/json' \
    --data '{
        "full_name": "User One"
    }'
  ```
- Example jwt token (debug it in [JWT.io](https://jwt.io/)):  
  ```
  eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIzNWRiYTBjNC1iYTE5LTQ5MTYtYTY1OC0xZTE4NWQwNGYwODYiLCJleHAiOjE1OTI3NzI1MzR9.sNXEEIE68CZ-IAjnTCqc2RvgBrRuwMJ5Kve6KJClXNM
  ```
