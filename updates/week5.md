# Week 5 meeting and activities

_(June 25,2024)_

## Attendees

-   [Divij Sharma](https://github.com/dvjsharma)
-   [Gaurav Mishra](https://github.com/GMishx)
-   Katharina Ettinger
-   [Shaheem Azmal M MD](https://github.com/shaheemazmalmmd)

## Discussion

-   **One Shot Analysis**

    -   Showed demo on the One Shot Analysis endpoints. The endpoints are used to run Nomos, Monk and CEU scans on the uploaded file.
    -   Raised a concern about `start` and `end` parameters in the highlights object are casted as string in the response. Got a suggestion to cast them as integer.
    -   Shared that the endpoints don't return the scanned text, as passing it in the response will make the server slow and is not a requirement either. Scanned text can always be processed on the client side. Got positive feedback on this.

-   **User Copyright Findings**

    -   Showed screenshots of the new endpoints to get/delete/restore/update/count user copyright findings. The endpoints are used to manage the user copyright findings.
    -   No concerns were raised about these endpoints.
    -   Will need to implement similar endpoints for scancode findings for copyright, email, author and URL.
    -   Asked about the necessity of `count` endpoint. It can be skipped as of now as it was a user request specifically for `copyright` endpoint, which is already implemented.

-   **OAuth 2.0 Authorization Code Flow**

    -   Showed a demo on the OAuth 2.0 Authorization Code Flow. The endpoints are used to get the authorization redirect URL from the server and exchange the authorization code for an access token.
    -   Following concerns were raised:
        -   Since the flow type is Authorization Code, the user should not add the client in their list of active clients. The client should be added by the server admin in FOSSology configuration only.
        -   Since the client is no longer added by the user, the current auth flow will not work as we were authorizing the client based on the client id they have added.
    -   Got a suggestion to use the `/userinfo` endpoint to get the user details based on the access token and then authorize the client based on the user details.

## Activities

-   Added 12 new endpoints to expose operations for scancode findings for copyright, email, author and URL.

    1. Added the following new endpoints for scancode copyright findings.

    -   GET `uploads/{id}/item/{itemId}/scancode-copyrights` : To retrieve scancode copyright findings.
    -   DELETE `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}` : To deactivate scancode copyright.
    -   PATCH `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}` : To restore deactivated scancode copyright.
    -   PUT `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}` : To update scancode copyright.
    2. Added the following new endpoints for scancode email findings.

    -   GET `uploads/{id}/item/{itemId}/scancode-emails` : To retrieve scancode email findings.
    -   DELETE `uploads/{id}/item/{itemId}/scancode-emails/{hash}` : To deactivate scancode email.
    -   PATCH `uploads/{id}/item/{itemId}/scancode-emails/{hash}` : To restore deactivated scancode email.
    -   PUT `uploads/{id}/item/{itemId}/scancode-emails/{hash}` : To update scancode email.
    3. Added the following new endpoints for scancode url findings.

    -   GET `uploads/{id}/item/{itemId}/scancode-urls` : To retrieve scancode url findings.
    -   DELETE `uploads/{id}/item/{itemId}/scancode-urls/{hash}` : To deactivate scancode url.
    -   PATCH `uploads/{id}/item/{itemId}/scancode-urls/{hash}` : To restore deactivated scancode url.
    -   PUT `uploads/{id}/item/{itemId}/scancode-urls/{hash}` : To update scancode url.
    4. Added the following new endpoints for scancode author findings.

    -   GET `uploads/{id}/item/{itemId}/scancode-authors` : To retrieve scancode author findings.
    -   DELETE `uploads/{id}/item/{itemId}/scancode-authors/{hash}` : To deactivate scancode author.
    -   PATCH `uploads/{id}/item/{itemId}/scancode-authors/{hash}` : To restore deactivated scancode author.
    -   PUT `uploads/{id}/item/{itemId}/scancode-authors/{hash}` : To update scancode author.

    Uplink PR [feat(api): New endpoints to get/delete/restore/update scancode copyright, email, author, url findings](https://github.com/fossology/fossology/pull/2772)

-   Updated the `start` and `end` parameters in the highlights object to be casted as integer in the response.
    
    Uplink PR [feat(api): Added OneShot analysis endpoints for license & copyright](https://github.com/fossology/fossology/pull/2768)

## Screenshots

-   GET `uploads/{id}/item/{itemId}/scancode-copyrights` : To retrieve scancode copyright findings.
    ![get](../static/scancodecopyrightget.png)
-   DELETE `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}` : To deactivate scancode copyright.
    ![delete](../static/scancodecopyrightdelete.png)
-   PATCH `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}` : To restore deactivated scancode copyright.
    ![patch](../static/scancodecopyrightpatch.png)
-   PUT `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}` : To update scancode copyright.
    ![put](../static/scancodecopyrightput.png)

_Screenshots are similar for `email`, `url` and `author` endpoints._

