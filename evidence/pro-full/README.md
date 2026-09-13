# Pro Full / Codex-Work incident

## Scope

This evidence family covers the September 8–10, 2026 account-selective failure affecting a higher-tier paid account referred to in the public record as **Pro Full**. A second paid identity, **Pro Light**, was used as the comparison.

The comparison used the same Windows laptop, surrounding browser environment, home network, and VPN configuration. The checks were performed in Hermes and in the official ChatGPT Work interface, including account switching inside the same browser.

## Public fingerprint

Exact provider-incident projection:

```text
SHA-256 954baeaf3e308ae877a381abfabcd4ab44b50b359666733294d92166b6777025
```

A related public technical report is available at:

- [Hermes issue #107307](https://github.com/NousResearch/hermes-agent/issues/107307)

## Observed comparison

| Account / route | Observed result |
|---|---|
| Pro Full, Hermes / `openai-codex` | repeated overload failures |
| Pro Full, official ChatGPT Work in Edge | overload/capacity failure for affected model paths; GPT-5.5 later returned a response |
| Pro Full, official ChatGPT Work in Yandex Browser | overload/capacity failure for affected model paths |
| Pro Full, ordinary ChatGPT conversation mode | worked |
| Pro Light, official ChatGPT Work in the same browser | worked |

The historical log audit recorded 151 main-loop overloaded attempts, 11 additional auxiliary overload failures, and 1,987 successful Codex calls in the detailed window. The report distinguishes overloads from 429 rate-limit events and other errors.

## What this evidence supports

- the failure reproduced outside Hermes;
- the observed failure followed the paid account and route more closely than the local machine alone;
- the incident was model- and route-dependent rather than a claim that every Codex operation on the account always failed;
- the same surrounding environment produced different results for the two paid identities.

## What this evidence does not establish by itself

- OpenAI's private server-side root cause;
- an anti-abuse action, physical server allocation, or particular entitlement mechanism;
- that all models or all Codex execution on Pro Full were unavailable;
- that a successful GPT-5.5 response established durable recovery;
- a legal conclusion about the subscription.

Private session archives, credentials, task content, and raw logs remain outside this repository.
