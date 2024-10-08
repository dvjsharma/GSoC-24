# Week 1 meeting and activities

*(May 30,2024)*

## Attendees

- [Divij Sharma](https://github.com/dvjsharma)
- [Gaurav Mishra](https://github.com/GMishx)
- [Samuel Dushimimana](https://github.com/dushimsam)
- [Shaheem Azmal M MD](https://github.com/shaheemazmalmmd)
- [Soham Banerjee](https://github.com/soham4abc)
- [Valens Niyonsenga](https://github.com/valens200)

## Discussion

- **Who should be doing what?**
  - Discussed project responsibilities with my colleague [Valens](https://github.com/valens200) and mentors.
  - We decided that currently I will focus on the REST API Version 2 upgrade and OAuth 2.0 implementation, while Valens would work on adding test cases for the current REST API implementation.

- **REST API Version 2 updates**
  - I mentioned that the work on the REST API Version 2 upgrade is almost complete and suggested we can start looking for any further improvements.
  - Mentors suggested I should review the code and look for any possible improvements based on my proposed guidelines. [(REST API Guidelines)](https://fossology.github.io/gsoc/docs/2024/rest/API-guidelines).

- **OAuth 2.0 architecture discussion and needs**
  - [Gaurav](https://github.com/GMishx) explained the various modes of authentication we aim to have in the FOSSology project. These are:
    - Token based authentication
    - Authorization Code Grant (Web Application)
    - Client Credentials Grant (Machine to Machine)
  - I cleared my doubts regarding the OAuth 2.0 implementation and its significance in the project. I also got a rough vision of what needs to be implemented and what is already implemented. [(Reference Material)](https://github.com/fossology/fossology/wiki/OpenID-Connect-authentication-configuration)

## Activities

- Tested the REST API Version 2 on a local instance and noted down the improvements that can be made.
- Researched on OAuth 2.0 and how it can be implemented in the project.
- Did minor improvements in the following PR:
  - [feat(api): Upgrade User & Group APIs to Version 2 ](https://github.com/fossology/fossology/pull/2711)