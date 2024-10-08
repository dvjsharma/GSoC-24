# Week 4 meeting and activities

_(June 18,2024)_

## Attendees

-   [Divij Sharma](https://github.com/dvjsharma)
-   [Gaurav Mishra](https://github.com/GMishx)
-   [Shaheem Azmal M MD](https://github.com/shaheemazmalmmd)

## Discussion

-   Gave updates and demo on previous week's work.
-   Discussed on the endpoint requirements for the One Shot Analysis and User Copyright Findings.
-   Resolved some queries regarding the architecture of APIs.

## Activities

-   **One Shot Analysis**

    -   Exposed 3 new endpoints to enable One Shot Analysis in the REST API:
        -   `/uploads/oneshot/nomos` to run a Nomos scan on the uploaded file.
        -   `/uploads/oneshot/monk` to run a Monk scan on the uploaded file.
        -   `/uploads/oneshot/ceu` to run Copyright, Email and URL scan on the uploaded file.
    -   All of these endpoints accept a file binary and return the scan results in the following format:
        -   **Data Type** : What is the scan returning (Nomos, Monk, CEU). Can take values like `license` and `copyright`.
        -   **Highlight** : The highlighted text in the scan results based on the data type (license, copyright, emails, URLs etc).
    -   Decided on not returning the scanned file in the response as it increases unnecessary load on the server. It can always be accessed from the frontend.
    -   Uplink PR: [feat(api): Added OneShot analysis endpoints for license & copyright](https://github.com/fossology/fossology/pull/2768)

-   **User Copyright Findings**

    -   Exposed 5 new endpoints to enable User Copyright operations in the REST API:
        -   `/uploads/{id}/item/{itemId}/user-copyrights` to retrieve user copyright findings.
        -   `/uploads/{id}/item/{itemId}/user-copyrights/{hash}` to deactivate user copyright findings.
        -   `/uploads/{id}/item/{itemId}/user-copyrights/{hash}` to restore deactivated user copyright findings.
        -   `/uploads/{id}/item/{itemId}/user-copyrights/{hash}` to update user copyright findings.
        -   `/uploads/{id}/item/{itemId}/totalusercopyrights` to get the count of user copyright findings.
    -   Uplink PR: [feat(api): New endpoints to get/delete/restore/update user copyright findings](https://github.com/fossology/fossology/pull/2717)

-   **OAuth 2.0 Authorization Code Flow**

    -   Created the complete OAuth 2.0 Authorization Code Flow for the new UI.
    -   Exposed the following endpoints to enable the mechanism:
        -   `/oauth/login` to get the authorization redirect URL from the server.
        -   `/oauth/callback` to exchange the authorization code for an access token.
    -   Below is how the flow works:
        -   Frontend will hit the `/oauth/login` endpoint to get the authorization URL and will be redirected to the authorization URL for the user to log in.
        -   User will log in and authorize the client application, and they will be redirected back to the frontend with an authorization code and a state (to prevent CSRF attacks).
        -   Frontend will hit the `/oauth/callback` endpoint with the authorization code and state to get the access token. The access token will be stored in the frontend and will be used to access the FOSSology API.
            -   The authorization code will be exchanged for an access token by the FOSSology server using the configs.
            -   This token will be decoded, and the user will be authenticated if they have the same `client id` added in their active clients.
            -   The drawback with this is the the user needs to know the client id to access the API.
    -   Made a client side application [OAuthFossy](https://github.com/dvjsharma/OAuthFossy) to test the flow.
    -   Uplink PR: [feat(oauth): Added Authorization Code Grant OAuth functionality](https://github.com/fossology/fossology/pull/2761)

## Screenshots

-   **One Shot Analysis**

    -   POST `/uploads/oneshot/nomos` to run a Nomos scan on the uploaded file.
        ![Nomos](../static/nomos.png)
    -   POST `/uploads/oneshot/monk` to run a Monk scan on the uploaded file.
        ![Monk](../static/monk.png)
    -   POST `/uploads/oneshot/ceu` to run Copyright, Email and URL scan on the uploaded file.
        ![CEU](../static/ceu.png)

-   **User Copyright Findings**

    -   GET `/uploads/{id}/item/{itemId}/user-copyrights` to retrieve user copyright findings.
        ![get](../static/usercopyrightget.png)
    -   DELETE `/uploads/{id}/item/{itemId}/user-copyrights/{hash}` to deactivate user copyright findings.
        ![delete](../static/usercopyrightdelete.png)
    -   PATCH `/uploads/{id}/item/{itemId}/user-copyrights/{hash}` to restore deactivated user copyright findings.
        ![patch](../static/usercopyrightpatch.png)
    -   PUT `/uploads/{id}/item/{itemId}/user-copyrights/{hash}` to update user copyright findings.
        ![put](../static/usercopyrightput.png)
    -   GET `/uploads/{id}/item/{itemId}/totalusercopyrights` to get the count of user copyright findings.
        ![count](../static/usercopyrightcount.png)

-   **OAuth 2.0 Authorization Code Flow**

    -   GET `/oauth/login` to get the authorization redirect URL from the server.
        ![login](../static/login.png)
    -   POST `/oauth/callback` to exchange the authorization code for an access token.
        ![callback](../static/callback.png)
