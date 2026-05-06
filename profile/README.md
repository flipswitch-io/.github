 API key, ship.

## Quick start

```ts
import { FlipswitchServerProvider } from '@flipswitch-io/server-provider';
import { OpenFeature } from '@openfeature/server-sdk';

await OpenFeature.setProviderAndWait(
  new FlipswitchServerProvider({ apiKey: process.env.FLIPSWITCH_API_KEY })
  );

const client = OpenFeature.getClient();
const showFeature = await client.getBooleanValue('checkout-redesign', false, {
  targetingKey: user.id,
    plan: user.plan,
    });
    ```

Five minutes to first flag:
[docs.flipswitch.io/docs/getting-started/quick-start](https://docs.flipswitch.io/docs/getting-started/quick-start).

## SDKs

| Language | Repo | Install |
|----------|------|---------|
| JavaScript / TypeScript | [`js-sdk`](https://github.com/flipswitch-io/js-sdk) | `@flipswitch-io/server-provider`,
`@flipswitch-io/web-provider` |
| Python | [`python-sdk`](https://github.com/flipswitch-io/python-sdk) | `flipswitch-provider` on PyPI |
| Go | [`go-sdk`](https://github.com/flipswitch-io/go-sdk) | `github.com/flipswitch-io/go-sdk` |
| Java | [`java-sdk`](https://github.com/flipswitch-io/java-sdk) | `io.flipswitch:flipswitch-sdk` on Maven Central |

All MIT-licensed. All built on top of the official OpenFeature SDKs, no proprietary fork.

## Why Flipswitch

- **OpenFeature-native.** Drop-in provider. Switching vendors later means changing one line, not rewriting every flag check.
- **Server-side evaluation via OFREP.** Targeting rules stay on the server. SDKs are thin HTTP clients with SSE for real-time updates,
so no evaluation engine to maintain in N languages.
- **Real-time updates on every plan, free included.** Some vendors gate streaming behind a paid tier; we don't.
- **Free tier, no credit card.** Side projects use it forever. Teams upgrade when they actually need to.

Architecture deep dive: [Server-Side vs Client-Side Evaluation](https://flipswitch.io/articles/server-side-vs-client-side-evaluation).

## Coming from another vendor?

- [Migrating from LaunchDarkly](https://docs.flipswitch.io/docs/guides/migrating-from-launchdarkly)

## Resources

- **Product**: [flipswitch.io](https://flipswitch.io)
- **App**: [app.flipswitch.io](https://app.flipswitch.io)
- **Docs**: [docs.flipswitch.io](https://docs.flipswitch.io)
- **Articles**: [flipswitch.io/articles](https://flipswitch.io/articles)
- **Status**: [status.flipswitch.io](https://status.flipswitch.io)
- **MCP server for coding agents**: [docs.flipswitch.io/docs/agents](https://docs.flipswitch.io/docs/agents)

---

Built for developers who'd rather ship than file tickets.
