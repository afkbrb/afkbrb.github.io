# GSoC 2020: Enhancements for Wikidata extension

During GSoC 2020, I added two features to the Wikidata extension:

1. OAuth support for Wikidata extension ([#2661](https://github.com/OpenRefine/OpenRefine/pull/2661))
2. Extend Wikidata extension to support arbitrary Wikibase instances ([#2810](https://github.com/OpenRefine/OpenRefine/pull/2810))

Since these two features are not quite relevant, I'll give introduce them separately.

## OAuth support

The original goal was to add three-legged OAuth support to the Wikidata extension, so users can authorize OpenRefine to upload edits to Wikidata on behalf of them without providing their usernames and passwords to OpenRefine. But considering that OpenRefine was designed to be used locally by a single user, and due to some reasons under [#2661](https://github.com/OpenRefine/OpenRefine/pull/2661), we found that three-legged OAuth support is complex and not useful. So, the goal was changed to adding two-legged OAuth support (i.e.,  supporting login with [owner-only consumer](https://www.mediawiki.org/wiki/OAuth/Owner-only_consumers)).

### Outcome

Users can now choose to login with owner-only consumer. This is helpful for the security of their Wikidata accounts.

![](./imgs/login-with-owner-only-consumer.png)

After clicking on "login with your owner-only consumer", the user can use the consumer credentials to login in the following dialog:

![](./imgs/login-with-owner-only-consumer1.png)

### TODO

- Add three-legged OAuth support when OpenRefine introduces a use system and supports multiple users, but that's a long way to go.

## Arbitrary Wikibase instances support

