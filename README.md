# EUDIPLO examples

Example services that show how to integrate with [EUDIPLO](https://github.com/EUDIPLO/eudiplo). They are for development and testing only and are not part of an EUDIPLO release.

| Folder | What it is | Local URL |
| --- | --- | --- |
| [`webhook/`](./webhook) | Webhook receiver and attribute provider: claims, notification and presentation webhooks (Cloudflare Worker) | `http://localhost:8787` |
| [`kms-reference/`](./kms-reference) | Reference service for EUDIPLO's `http` KMS provider; keys live in memory (Cloudflare Worker) | `http://localhost:8788` |

The contracts these services implement are specified in the EUDIPLO documentation:

- [Webhooks](https://eudiplo.dev/docs/reference/webhooks) and the [attribute provider API](https://eudiplo.dev/docs/reference/attribute-provider-api)
- [HTTP provider API](https://eudiplo.dev/docs/reference/kms-config#http-provider-api) of the KMS

If the documentation and an example disagree, the documentation is right.

## Run locally

```bash
pnpm install
pnpm --filter test-rp dev        # webhook/ on :8787
pnpm --filter kms-reference dev  # kms-reference/ on :8788
```

EUDIPLO rejects HTTP and loopback targets by default. Set `OUTBOUND_URL_ALLOW_HTTP=true` and `OUTBOUND_URL_ALLOW_PRIVATE_NETWORK=true` on the backend to call them.

## History

Both folders were moved here from `apps/webhook` and `apps/kms-reference` of the EUDIPLO repository, with their commit history.

## Contributing

Same rules as the main repository: see [CONTRIBUTING.MD](https://github.com/EUDIPLO/eudiplo/blob/main/CONTRIBUTING.MD). Every commit is signed off (`git commit -s`).
