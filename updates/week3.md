# Week 3 meeting and activities

_(June 11,2024)_

## Attendees

-   [Divij Sharma](https://github.com/dvjsharma)
-   [Gaurav Mishra](https://github.com/GMishx)
-   [Shaheem Azmal M MD](https://github.com/shaheemazmalmmd)

## Discussion

-   **OAuth**
    -   Proposed 2 mechanisms for OAuth 2.0 implementation in the project.
        -   **M-2-M, for technical uesrs**:
            -   Clients must obtain a token from the authorization server using their client ID and client secret.
            -   The token can be used to access the FOSSology API.
            -   For this to happen, FOSSology server must be configured to use OAuth 2.0.
            -   REST API will have endpoints to do this configuration.
            -   Token sent should be verified by the server and user should be authenticated and authorized.
        -   **Authorization Code Grant, for end users and new UI**:
            -   Only for client applications that can interact with the user.
            -   Can use various npm libraries to implement this flow.
            -   Users will log in and receive a code.
            -   This code can be exchanged for a token to access the FOSSology API.
    -   [Gaurav](https://github.com/GMishx) mentioned that the `client id` for both the mechanisms will be different, which will cause problems when using the same client for both the mechanisms.
    -   We will have to look into this and find a solution. Maybe I will handle this in the last week.
    -   Discussed the improvements that can be made in the REST API Version 2, particularly the status codes and pagination.

## Activities

-   **OAuth 2.0 M-2-M implementation**

    -   Implemented the OAuth 2.0 M-2-M mechanism for the project.
    -   Created an endpoint `/users/oauthclient` to add new clients when user is logged in.
    -   Created an endpoint `/users/oauthclient/{type}` to get active and expired OAuth clients.
    -   The `/customise` endpoint used to accept only a single key-value pair for updating admin configs, making it difficult to update fields in bulk. I've modified it to accept an array of key-value pairs and update accordingly.
    -   The `/customise` endpoint is now capable to fetch all other URLs required for OIDC integration when the discovery URL is passed over the REST API.
    -   Raised a PR [feat(oauth): Added machine-to-machine OAuth functionality](https://github.com/fossology/fossology/pull/2761) for the same.

-   **REST API Version 2**
    -   Started working on the improvements identified in the last meeting:
        -   Status Codes: Particularly 204 (no content)
        -   Adding pagination to all necessary endpoints
        -   Using model classes for all major/minor responses
        -   Test coverage
        -   Authentication workflow
    - Made requested changes in the PR [feat(api): Upgrade Jobs & Report APIs to Version 2](https://github.com/fossology/fossology/pull/2736).

## SecreenShots

-   `/users/oauthclient` : Add new clients when user is logged in.
    ![addclients](../static/addclients.png)
-   `/users/oauthclient/{type}` : Get active and expired OAuth clients.
    ![viewclients](../static/viewclients.png)
