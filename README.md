# @nostream/sdk
Library that support Nostr messges


Alice
nsec18c4t7czha7g7p9cm05ve4gqx9cmp9w2x6c06y6l4m52jrry9xp7sl2su9x

Bob
nsec1zsp48upz3vd64lwhx7me8utrxyfxuzdwvxhfld2q0ehs0ya9mlxs47v64q


Config local repo
npm config set registry http://localhost:4873


Step the version
npm version prerelease --preid snapshot

## CI Publish (Granular Token, no OTP prompts)

Use a granular npm token with publish permission and 2FA bypass enabled, then add it as a GitHub Actions secret.

### One-time setup

1. In npm, create a granular access token:
- Resource: package `@nostream/sdk` (or org-level package publish scope)
- Permission: `Read and write`
- Enable: `Bypass 2FA for package publishing`

2. In GitHub repo `DarkWebDivingClub/nostream-sdk`, add secret:
- Name: `NPM_TOKEN`
- Value: the granular token

3. Release flow:
- `npm version patch` (creates commit + tag)
- `git push origin main --tags`

Pushing the `v*` tag triggers `.github/workflows/publish.yml` to publish automatically.
