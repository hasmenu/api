## Has.Menu API

### Introduction

Has.Menu is an online service to discover restaurant menus.
This API describes the interface to client-side applications
tools and utilities to work with Has.Menu data.

### Version

The API is version controlled. Every request should explicitly
mention the version via the <code>Accept</code> header.

    Accept: application/vnd.hasmenu+json; version=1

Current version of the API is 1.

### API

The current version of API is available at
https://github.com/hasmenu/api/blob/master/versions/v1/api.md

### Restrictions

- All API access is over HTTPS
- The URL should be in the format https://<city>.has.menu/<restful-url-fragments>
- The request payload for POST is always JSON, i.e. Content-Type: application/json
- For personal and social requests HasMenu-Auth-Key should be present in the header
- The API is rate-limited to 60 requests per minute

### License

Has.Menu publishes the API to create applications to access and interact with
Has.Menu ecosystem. Using this API, you should explicitly mention Has.Menu
in your apps, tools, utilities, or in any form of creations. However, you are
not allowed to officially represent or claim and endorsement from Has.Menu unless
certified with our developer program.

Has.Menu retains the rights over the data, the data schema and the API.

You are permitted to use Has.Menu data and API to:

- Build client-side apps for individual use
- Integrate menus in your restaurant websites

You are not permitted to host Has.Menu data, or sell it to third-parties.

You are not permitted to use Has.Menu API to replicate Has.Menu data without
explicit permission. If you require large volume data for research and analysis
you should contact Has.Menu directly with the objectives and need for the research.

You should use the API in a manner that does not exceed a resonable request volume.
We may blacklist the email, IP, or any such identifiable information if you fail
to comply with this.

Has.Menu reserves the right to modify the API, and potentially introduce breaking
changes within a version. Every modification of the API will be documented, and
you are required to keep up-to-date with the documentation.

This license and agreement is in effect, from the moment you access the API for
the first time.

If you have any questions, please send a mails to developers@has.menu
