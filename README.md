


<h1 align="center">Google Summer of Code 2024 <img src="https://media2.giphy.com/media/KB8MHRUq55wjXVwWyl/source.gif" width="50"></h1>

![ViewCount](https://views.whatilearened.today/views/github/dvjsharma/GSoC-24.svg)
![GitHub](https://img.shields.io/github/followers/dvjsharma?style=social)
![Twitter](https://img.shields.io/twitter/follow/DvjShx?style=social)
![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)

<div align = "center">
    <img src="https://github.com/user-attachments/assets/94976eda-9d37-4bbe-862a-154984209d8a"/>
</div>

<div align = "center"><h2><i>REST API Improvements
 @ <a href = "https://www.fossology.org/">FOSSology </a> </i></h2></div>

<p align="center">
	<a href="#project-details">Project Details</a> | 
	<a href="#contributions">Contributions</a> | 
	<a href="#documentation">Documentation</a> | 
	<a href="#deliverables">Deliverables</a> | 
	<a href="#key-takeaways">Key Takeaways</a> |
    <a href="#acknowledgements">Acknowledgements</a> |
    <a href="#connections">Get In Touch</a>
</p>

<h1 align = "center" id = "project-details">📝 Project Details</h1>

## Overview

<p align="justify">
In recent years, FOSSology's REST APIs have expanded significantly, enhancing user accessibility, flexibility, and automation. However, the development is not yet complete, prompting some users to resort to mocking WebUI access solely for information retrieval. With the development of FOSSology's new React UI also underway, robust support for REST APIs becomes imperative. This project aims to finalize the development of FOSSology's REST API by exposing any remaining endpoints, enhancing and upgrading existing ones to V2, increasing test coverage, and improving documentation. The approach involves a comprehensive review of each module to ensure the availability and exposure of required APIs for frontend consumption. These efforts will streamline development workflows, enhancing the overall usability of the FOSSology platform and facilitating the development of the new React UI.
</p>

## Milestones and Tasks

### Milestone 1: Complete addition of all new endpoints as mentioned in the tasks

-   **M 1.1** : Copyright Browser.
-   **M 1.2** : One-Shot.
-   **M 1.3** : Jobs.
-   **M 1.4** : Any additional/new endpoints.

### Milestone 2: Complete upgradation & improvement of all endpoints as mentioned in tasks

-   **M 2.1** : Upgrade & Improve `/auth`, `/info`, `/upload` endpoints.
-   **M 2.2** : Upgrade & Improve `/copyright`, `/organize`, `/search`, `/user` endpoints.
-   **M 2.3** : Upgrade & Improve `/admin`, `/jobs`, `/folder` endpoints.
-   **M 2.4** : Upgrade & Improve `/group`, `/report`, `/licence`, `/maintenance`, `/overview` endpoints.

### Milestone 3: Complete addition of Unit tests for all endpoints as mentioned in task

-   **M 3.1** : Add Unit Tests for `/auth`, `/info`, `/upload`, `/organize`, `/user` endpoints.
-   **M 3.2** : Add Unit Tests for `/copyright`, `/search`, `/admin` endpoints.
-   **M 3.3** : Add Unit Tests for `/job`, `/folder`, `/group`, `/report`, `/licence`, `/maintenance`, `/overview` endpoints.

### Milestone 4: Additional Tasks

-   **M 4.1** : Provide OAuth 2.0 support with client credentials grant flow and authorization code grant flow over the APIs.
-   **M 4.2** : Complete any additional tasks as specified by the mentors.

<h1 align = "center" id = "contributions">🚀 Contributions</h1>

During my participation in the Google Summer of Code (GSoC) program, I focused on implementing and enhancing the following key features in the project:

1. ### Development of REST API upgrade guidelines:

    <p align="justify">
    I developed a comprehensive REST API upgrade guideline in preparation for the transition to version 2. This guideline was crucial in clearly defining the upgrade objectives and ensuring a smooth and effective process. The guideline is live on <a href="https://fossology.github.io/gsoc/docs/2024/rest/API-guidelines">this</a> link.
    </p>

2. ### Upgradation of REST APIs to Version 2:

    <p align="justify">
    I utilized this guideline to successfully upgrade the existing REST APIs to version 2, ensuring that all enhancements aligned with the predefined objectives and delivered a more robust and efficient API framework.
    </p>

3. ### Development of new endpoints:

    <p align="justify">
    I introduced several new endpoints to extend the platform's functionality. These new endpoints were designed to meet evolving user needs, streamline workflows, and provide more comprehensive access to the system's features, further enhancing the overall user experience. Also, since the new React UI is under development, these endpoints will also help in extending the backend functionality and removing the dependency on mocking WebUI access.
    </p>

4. ### Improving test coverage:

    <p align="justify">
    I worked with my colleague <a href="https://github.com/valens200">Valens</a> to improve the test coverage for existing functionalities and develop new test cases for new functionalities.
    </p>

5. ### Implement OAuth 2.0 authentication:

    <p align="justify">
    I exposed new endpoints to enable OAuth authentication over the APIs following the client credentials flow (for developers) and authorization code grant flow (for the new UI). This addition included authentication logic change in the backend.
    </p>

Let's dive deep into each category in more detail to showcase all the contributions, with the corresponding tests in screenshots where applicable, and the respective links to the Pull requests.

## Upgradation of REST APIs to Version 2 👨‍💻 :

1. Upgrade `/uploads` API to version 2.
    - [feat(api): (1) Upgrade Upload APIs to Version 2](https://github.com/fossology/fossology/pull/2633)
2. Upgrade `/user` and `/group` APIs to version 2.
    - [feat(api): Upgrade User & Group APIs to Version 2](https://github.com/fossology/fossology/pull/2711)
3. Upgrade `/folder`, `/license` and `/obligation` APIs to version 2.
    - [feat(api): Upgrade Folder, License & Obligation APIs to Version 2](https://github.com/fossology/fossology/pull/2712)
4. Upgrade `/jobs` and `/report` APIs to version 2.
    - [feat(api): Upgrade Jobs & Report APIs to Version 2](https://github.com/fossology/fossology/pull/2736)
5. Upgrade `/search`, `/copyright` and `/admin` APIs to version 2.
    - [feat(api): Upgrade Search, Copyright & Admin APIs to Version 2](https://github.com/fossology/fossology/pull/2744)

## Development of new endpoints 👨‍💻 :

1. Developed new endpoints for the `/copyright` API to support the retrieval, deletion, restoration and update of user copyright findings. Also, user can get the total user copyright count as well.

    - [feat(api): New endpoints to get/delete/restore/update user copyright findings](https://github.com/fossology/fossology/pull/2717)

    Make a `GET` request to the endpoint: `uploads/{id}/item/{itemId}/user-copyrights`.

    ![image](https://github.com/fossology/fossology/assets/119073504/d89aa9cf-b38d-4b92-84f1-6ed8ccf5670c)

    Make a `DELETE` request to the endpoint: `uploads/{id}/item/{itemId}/user-copyrights/{hash}`.

    ![Screenshot from 2024-06-20 03-26-22](https://github.com/fossology/fossology/assets/119073504/a9b72fd3-1001-4086-9c79-1a34ccf44e2d)

    Make a `PATCH` request to the endpoint: `uploads/{id}/item/{itemId}/user-copyrights/{hash}`.

    ![Screenshot from 2024-06-20 03-26-32](https://github.com/fossology/fossology/assets/119073504/42e2b7e1-f878-45dc-9b32-08ddeaed2e0b)

    Make a `PUT` request to the endpoint: `uploads/{id}/item/{itemId}/user-copyrights/{hash}`.

    ![Screenshot from 2024-06-20 03-27-25](https://github.com/fossology/fossology/assets/119073504/7b1a1717-8d15-4198-96dc-4a0bc8d185c5)

    Make a `GET` request to the endpoint: `uploads/{id}/item/{itemId}/totalusercopyrights`.

    ![image](https://github.com/fossology/fossology/assets/119073504/9d1d99b6-1f4c-4cd6-a50c-ea436f33b7a3)

2. Added 3 new endpoints to enable one-shot analysis functionality using Nomos, Monk, and copyright scanners:

    - [feat(api): Added OneShot analysis endpoints for license & copyright](https://github.com/fossology/fossology/pull/2768)

    Make a `POST` request to the endpoint: `/uploads/oneshot/nomos` along with the file to be scanned.

    ![image](https://github.com/fossology/fossology/assets/119073504/362d52e3-7224-4f32-887a-55f1de8954d4)

    Make a `POST` request to the endpoint: `/uploads/oneshot/monk` along with the file to be scanned.

    ![image](https://github.com/fossology/fossology/assets/119073504/9c151d00-410b-4e55-b326-3b13f55e8b79)

    Make a `POST` request to the endpoint: `/uploads/oneshot/ceu` along with the file to be scanned.

    ![image](https://github.com/fossology/fossology/assets/119073504/8cc905b0-52db-4339-8c52-60da46f7c917)

3. Developed new endpoints for the `/copyright` API to support the retrieval, deletion, restoration and update of scancode, email, author and url findings.

    - [feat(api): New endpoints to get/delete/restore/update scancode copyright, email, author, url findings](https://github.com/fossology/fossology/pull/2772)

    Make a `GET` request to the endpoint: `uploads/{id}/item/{itemId}/scancode-copyrights`.

    ![image](https://github.com/fossology/fossology/assets/119073504/0ab94b96-f8bd-460f-bf5b-67db28ba9f3a)

    Make a `DELETE` request to the endpoint: `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}`.

    ![image](https://github.com/fossology/fossology/assets/119073504/590f5b2e-99e6-4276-b310-557af268f0ae)

    Make a `PATCH` request to the endpoint: `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}`.

    ![image](https://github.com/fossology/fossology/assets/119073504/38851d5c-b63f-4fd2-9385-2d4009fae646)

    Make a `PUT` request to the endpoint: `uploads/{id}/item/{itemId}/scancode-copyrights/{hash}`.

    ![image](https://github.com/fossology/fossology/assets/119073504/d7c886e9-0b3c-483c-a82c-276211064fbd)

    _In the similar way, `email`, `url` and `author` endpoints can also be tested._

4. Developed new endpoints to provide JSON format import and export of licenses and obligations via APIs

    - [feat(api): JSON format export/import of licenses and obligations via APIs](https://github.com/fossology/fossology/pull/2804)

    Send a `GET` request to `/license/export-json` to test the license export functionality in JSON format.

    ![image](https://github.com/user-attachments/assets/6ef3da2a-6c78-413e-adaa-d14ec113b607)
    Send a `GET` request to `/obligations/export-json` to test the obligation export functionality in JSON format.

    ![image](https://github.com/user-attachments/assets/8a7d550b-cef5-49f9-b3c7-d907175d956d)

    Send a `POST` request to `/license/import-json` along with JSON file to import licenses.

    Send a `POST` request to `/obligations/import-json` along with JSON file to import obligations.

5. Modified the `/jobs` and related endpoints to provide more detailed information about the jobs and their status. Now, all the child jobs are included in the response, and the job status of each parent job is confined to all of its child jobs status exclusively. Additionally, the `/jobs/history` endpoint is deprecated in favour of the `/jobs` endpoint (in can be tweaked to get the history of jobs).

    - [feat(api): modify /jobs and related endpoints](https://github.com/fossology/fossology/pull/2781)

    For every distinct job, the `/jobs` endpoint now includes all the associated child jobs along with their detailed information.

    ![image](https://github.com/fossology/fossology/assets/119073504/269cb785-f120-4f5d-8744-e57a1b1abc49)

    The job status of each parent job is confined to its child job scope exclusively. If any other child job fails for the same upload, it won't affect the status of the current job.

    ![image](https://github.com/fossology/fossology/assets/119073504/da496486-05e2-45df-a21f-ea043eebb08b)
    ![image](https://github.com/fossology/fossology/assets/119073504/fb8c2452-9976-48f5-9857-057d16a82635)

## Implement OAuth 2.0 authentication 👨‍💻 :

<p align="justify">
In this milestone, I enhanced FOSSology server by adding new and improved API endpoints for OIDC configuration, making the server fully configurable via APIs. It also introduces support for the Client Credentials Grant (M2M) flow over APIs, allowing automated systems to authenticate and interact with FOSSology. Additionally, new endpoints enable the Authorization Code Grant flow, allowing web applications like FOSSologyUI to securely authenticate users and obtain access tokens. The same can be tested using the <a href="https://github.com/dvjsharma/OAuthFossy">OAuthFossy</a> web app.
</p>

#### Client Credentials

1. Added a new endpoint: `/users/oauthclient` to add a new OAuth client when the user is logged in.
    <div align = "center">
    <img src="https://github.com/fossology/fossology/assets/119073504/d4ba2abd-9430-4c60-87d8-36c7ecf04b58" width="80%"/>
    </div>

2. Added a new endpoint: `/users/oauthclient/{type}` to get active and expired OAuth clients.
    <div align = "center">
    <img src="https://github.com/fossology/fossology/assets/119073504/e2508ab4-8762-40ba-8dca-fa659adb9acf" width="80%"/>
    </div>

3. The `/customise` endpoint used to accept only a single key-value pair for updating admin configs, making it difficult to update fields in bulk. I've modified it to accept an array of key-value pairs and update accordingly. This change is done in version 2 APIs to maintain backward compatibility.

4. The `/customise` endpoint is now capable to fetch all other URLs required for OIDC integration automatically when the discovery URL is passed over the REST API.

#### Authorisation Code Grant

1. Added a new endpoint: `/oauth/login` to get the authorisation redirect URL. Client can redirect user to this URL where the user (resource owner) can grant access to their profile via OpenID.
    <div align = "center">
    <img src="https://github.com/fossology/fossology/assets/119073504/7817b762-a96f-437c-94b6-3e348d73e87a" width="80%"/>
    </div>

2. Added a new endpoint: `/oauth/callback` to exchange authorisation code with an access token. Once the user grants access to the resources, a `state` and `code` is generated which is later exchanged for an access token via this endpoint.
    <div align = "center">
    <img src="https://github.com/fossology/fossology/assets/119073504/ff2d932a-0444-4ad1-9f23-bac2271e7022" width="80%"/>
    </div>

## Other contributions 👨‍💻 :

1. [fix(api): Modified v2 YML file to accommodate v2 post upload request with multipart/form-data content type](https://github.com/fossology/fossology/pull/2705)
2. [fix(scancode): Fixed failing scancode agent when using FOSSology in Docker](https://github.com/fossology/fossology/pull/2692)
3. [feat(api): Add deprecation and sunset header ](https://github.com/fossology/fossology/pull/2808)
4. [feat(buildsystem): Introduce FORCE_CONF_OVERWRITE option to control configuration file overwrites](https://github.com/fossology/fossology/pull/2686)
5. [fix(action): Ensure proper handeling of enum values in argparse](https://github.com/fossology/fossology/pull/2647)

<h1 align = "center" id = "documentation">📄 Documentation</h1>

Throughout the 12 weeks of the GSoC period, I consistently created weekly documentation to track and record my progress. Week-wise documentation can be found in the following links:

-   [Week 1](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-05-30)
-   [Week 2](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-06-06)
-   [Week 3](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-06-11)
-   [Week 4](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-06-18)
-   [Week 5](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-06-25)
-   [Week 6](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-07-02)
-   [Week 7](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-07-09)
-   [Week 8](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-07-16)
-   [Week 9](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-07-23)
-   [Week 10](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-07-30)
-   [Week 11](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-08-06)
-   [Week 12](https://fossology.github.io/gsoc/docs/2024/rest/updates/Divij/2024-08-16)

<h1 align="center" id = "deliverables">👨🏻‍🏫 Deliverables</h1>

|                          Tasks                          | Planned |                                                       Completed                                                        |
| :-----------------------------------------------------: | :-----: | :--------------------------------------------------------------------------------------------------------------------: |
|           Develop REST API upgrade guidelines           |   Yes   |                                                   :heavy_check_mark:                                                   |
| Upgrade and improve all REST API endpoints to Version 2 |   Yes   |                                                   :heavy_check_mark:                                                   |
|   Add new endpoints as mentioned in the project list    |   Yes   |                                                   :heavy_check_mark:                                                   |
|        Add Support for OAuth 2.0 authentication         |   Yes   |                                                   :heavy_check_mark:                                                   |
|     Add API support for features under development      |   No    |                                                   :heavy_check_mark:                                                   |
|   Add unit tests for existing and new functionalities   |   Yes   | I contributed to 30% of the work, with the rest being handled by [Valens](https://github.com/valens200) in his project. |

<h1 align = "center" id = "key-takeaways">📚 Key Takeaways</h1>

-   Enhanced my problem-solving abilities by tackling complex challenges independently and creatively.
-   Developed proficiency in remote work culture.
-   Adapted to various technologies and tools, broadening my technical expertise.
-   Gained confidence in getting started and contributing to large codebases.
-   Embraced the culture of collaboration and teamwork.
-   Mastered time management while consistently meeting project deadlines.
-   Made significant progress in writing clean code and enhancing my coding proficiency.
-   Improved my skills in writing and understanding technical documentation for large-scale projects.
-   Made a lot of friends. :)

<h1 align = "center" id = "acknowledgements">🎓 Acknowledgements</h1>

<p align="justify">
    Contributing to FOSSology during Google Summer of Code has been a deeply personal and rewarding experience for me. As my first venture into open source, it has provided invaluable lessons and created memories that I will cherish for a lifetime. Although there are many people to thank, I would like to mention a few who have been my guiding lights throughout this journey.
    <br/>
    <br/>
    First and foremost, I would like to express my heartfelt gratitude to my mentors, <a href="https://github.com/shaheemazmalmmd" target="_blank">Shaheem Azmal M MD</a>, <a href="https://github.com/GMishx" target="_blank">Gaurav Mishra</a>, <a href="https://github.com/soham4abc" target="_blank">Soham Banerjee</a>, and <a href="https://github.com/dushimsam" target="_blank">Samuel Dushimimana</a>, for their unwavering support, guidance, and encouragement. These people are great to work with, are very polite, and have always been there to help me out whenever I needed it both professionally and personally. I am grateful for their mentorship and the opportunity to learn from them.
    <br/>
    <br/>
    I want to thank my friend and colleague <a href="https://github.com/akashsah2003" target="_blank">Akash</a> for his constant support and motivation throughout this journey. His encouragement and feedback have played a crucial role in my growth, and I am thankful for the positive influence and camaraderie we’ve shared.
    <br/>
    <br/>
    Finally, I want to thank my family and friends. I got to meet many awesome developers as my fellow participants from around the world. I wish we will do more collaboration in the future.
</p>

<h1 align = "center" id = "connections">🌐 Let's connect! </h1>

-   [![Twitter Badge](https://img.shields.io/twitter/follow/DvjShx?style=social)](https://twitter.com/DvjShx)
-   [![GitHub Badge](https://img.shields.io/badge/GitHub-%40dvjsharma-black?style=flat&logo=github)](https://github.com/dvjsharma)
-   [![LinkedIn Badge](https://img.shields.io/badge/LinkedIn-%40dvjsharma-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/dvjsharma/)
-   [![Email Badge](https://img.shields.io/badge/Email-divijs75%40gmail.com-red?style=flat&logo=gmail)](mailto:divijs75@gmail.com)