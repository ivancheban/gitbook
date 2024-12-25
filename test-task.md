Test Assignment - Technical Writer @
Apolo
Overview
Your goal is to create a user guide that walks users through the process of running Redis with
Apolo Jobs and CLI.
Redis is an open-source, in-memory data store commonly used as a database and cache.
The following aspects need to be addressed:
● Discovery: Explain how users can locate a publicly available container image, identify
its version, and record any essential details.
● Installation: Provide an explanation of the role Apolo Jobs play in the setup process,
along with the necessary configuration steps and the Apolo CLI commands required.
● Usage: Verify that a Redis job is operational, and describe how the database can be
accessed by other jobs or through the Apolo CLI using port-forwarding.
● Cleanup: Provide detailed steps to restore the system to its original state.
Onboarding
To work on the assignment, you need access to Apolo:
● You will receive an email invitation to join an organization in Apolo. Please follow the
steps there.
● Sign up using the email address where the invite was sent.
● Contact yevhenii.semendiak@apolo.us and oleksandr@apolo.us if you need any
assistance during the onboarding process.
Requirements
● The guide should be written in Markdown.
● The guide should assume the user is already authenticated with Apolo, has the CLI
installed, and has access to a compute cluster and project. However, these prerequisites
should be briefly mentioned at the beginning of the guide for clarity.
● The result should be uploaded to a private GitHub repository. Please grant access to
@dalazx, @YevheniiSemendiak, and @polinasndbx by adding them as
collaborators.
Extra Credit
The following additional features or improvements will be considered as bonus points but are
not required for the completion of the assignment.
● Include explanatory diagrams or graphics to make the guide more engaging and easier
to understand.
● Provide instructions on configuring the Redis job to use Apolo Files for persistence.