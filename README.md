# Some ansible to hit the Mastodon API

For now, we're faking it using [webhook.site](https://webhook.site/e8eda46a-85f3-4f39-853e-7c2dfc8f7b4d/api/v1/admin/measures) - to use it with the real Mastodon we would need to:

* put the real Mastodon URL into [group_vars](playbook/group_vars/all.yaml)
* store the real API key as a [Github Secret](https://docs.github.com/en/actions/security-guides/encrypted-secrets) called `MASTODON_TOKEN`

All this playbook does is hit the [measures](https://docs.joinmastodon.org/methods/admin/measures/#get) endpoint and then dump the response into the console - I have no idea if this is likely to contain any sensitive data because on my local install, with one user and one toot, it returned `[]`
