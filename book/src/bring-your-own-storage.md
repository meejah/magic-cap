# Bring Your Own Storage

It is very often the case that a user or developer already has some Internet-accessible storage.

For example, a GitHub account provides free storage.
Similarly, many people may already have AmazonS3, BackblazeB2, Digital Ocean or other cloud-provider storage that they pay for.

Magic Cap is eager to work within these systems, providing the "but private" layer on top of existing reliable storage.


## Using GitHub

Let us use a free GitHub account to store some Magic Cap data privately.

We can store whatever we like in this manner.
Only a computer with the Magic Cap and access to the GitHub repository may retrieve the plaintext.

* Create a new repository. I called my example [magic-cap-storage](https://github.com/meejah/magic-cap-storage).
* (optional) push a `README.md` to explain what's in it.
* (optional) in Settings, turn off "Wikis", "Issues", "Preserve this repository", "Projects" and "Pull requests".
* Create a "fine-grained personal access token":
  * note GitHub's warnings: this is like using your password etc DO NOT give this to anyone
  * we need "create a blob" and "create a commit" access under "git"
  * we use GitHub's "push access" example to grant extensive write access to our new repository
  * here is a link to create such a token in your own account:
    [create new token](https://github.com/settings/personal-access-tokens/new?name=Magic+Cap+token&description=Grant+contents:write+for+magic-cap+example&contents=write)
  * be sure to change Repository Access to "only select repositories" and select the newly-created one




NOTES:
- PRIVATE my token: 
- we want to do "GitHub API" stuff (right?) like create commits via Web client
- we need a token https://docs.github.com/en/rest/authentication/authenticating-to-the-rest-api?apiVersion=2026-03-10
- "fine-grained personal access token" allows access to only some REST APIs
  - i think we want "git" -> "commit" as in this:
    https://docs.github.com/en/rest/git/commits?apiVersion=2026-03-10#create-a-commit
  - ^ is available on fine-grained access token
  - maybe "create a blob" is enough?
    https://docs.github.com/en/rest/git/blobs?apiVersion=2026-03-10#create-a-blob
