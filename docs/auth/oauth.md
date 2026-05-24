# OAuth 2.0

In addition to API tokens, we support OAuth 2.0 for third-party
integrations.

## Authorization code flow

1. Redirect the user to:
   ```
   https://auth.example.com/oauth/authorize
     ?client_id=YOUR_CLIENT_ID
     &redirect_uri=YOUR_REDIRECT_URI
     &response_type=code
     &scope=read+write
     &state=RANDOM_STATE
   ```
2. The user approves
3. We redirect to your `redirect_uri` with `?code=AUTH_CODE&state=...`
4. Exchange the code for tokens:
   ```
   POST https://auth.example.com/oauth/token
   ```

## Scopes

Same scopes as API tokens: `read`, `write`, `admin`.

## Token refresh

Access tokens expire in 1 hour. Use the refresh token to get a new one.
