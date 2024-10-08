# Week 2 meeting and activities

*(June 6,2024)*

## Attendees

- [Divij Sharma](https://github.com/dvjsharma)
- [Shaheem Azmal M MD](https://github.com/shaheemazmalmmd)
- [Valens Niyonsenga](https://github.com/valens200)

## Discussion

  - No major updates since the last meeting.
  - Discussed the improvements that can be made in the REST API Version 2.
  - Discussed the implementation of OAuth 2.0 in the project.

## Activities

- **OAuth 2.0**
  - Researched OAuth 2.0 and its application on production servers. Found the [Auth0 article](https://auth0.com/intro-to-iam/what-is-oauth-2) particularly helpful. Studied various architectural patterns for different flows to determine the best fit for our project.
  - Prepared a draft outlining the implementation details, focusing on two scenarios:

    - **For the API**:
      - Create an endpoint to add new clients, accepting `name`, `clientId`, and `scope`.
      - Another endpoint to configure FOSSology, accepting `appName`, `clientId`, `clientSecret`, `clientClaim`, `redirectUri`, and `discoveryUri`. The `discoveryUri` will be used to fetch other required endpoints.
      - Once these steps are completed, FOSSology will be configured to use OAuth 2.0. Users can obtain a token from their authorization server to access the FOSSology API.

    - **For the Web Application**:
      - Implement the Authorization Code Grant flow for the frontend. This requires a login page where users can log in and receive a code, which can be exchanged for a token to access the FOSSology API.
      - Researched libraries to implement this flow on the frontend.
      - On the server side, implement a mechanism to verify user credentials received from the server and issue a token to the user.

- **REST API Version 2**
  - Reviewed the code and identified areas for improvement.
  - Found the following things which we can look into:
    - Status Codes: Particularly 204 (no content)
    - Adding pagination to all necessary endpoints
    - Using model classes for all major/minor responses
    - Test coverage
    - Authentication workflow