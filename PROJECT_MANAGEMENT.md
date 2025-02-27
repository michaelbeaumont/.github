# Project Management for Kuma

## Triage

The original doc for this is [there](https://docs.google.com/document/d/1k4Y-u54fBoquCv2ROaz_cNu45lmrZsuySxDVqCk2ud8/edit).

Triaging happens on a weekly basis on Mondays [Event invite](https://calendar.google.com/event?action=TEMPLATE&tmeid=Nm5yOHZoc2JmZmE5MWY0cXNlanRlZnZhdWpfMjAyMTExMjJUMTUwMDAwWiBjaGFybHkubW9sdGVyQGtvbmdocS5jb20&tmsrc=charly.molter%40konghq.com&scp=ALL).

In this meeting we will iterate over each repo in the kumahq github organization and take the following actions:

- Look at all tickets with `triage/pending` and take the following actions:
  - Set accurate `kind/*` and `area/*` labels
  - If a ticket is unclear set `triage/needs-information`
  - If a similar ticket already exists set `triage/duplicated` add a comment with the original ticket and close the newest ticket
  - If a ticket looks good, set `triage/accepted`. A ticket being accepted doesn’t mean someone will work on it, just that it’s looking good. However, a closed ticket with `triage/accepted` is work that was actually done.
- Look at all tickets with `triage/stale` and either remove the stale label if we think it’s still a valid ticket or set `triage/rotten` which will close the ticket

Here are the github search to do this:

- [all `triage/pending` issues in kumahq](https://github.com/search?l=&q=user%3Akumahq+label%3Atriage%2Fpending+state%3Aopen&type=issues)
- [all `triage/stale` issues in kumahq](https://github.com/search?l=&q=user%3Akumahq+label%3Atriage%2Fstale+state%3Aopen&type=issues)

## Tooling

In order to make this simple we've added some automation based mostly on github actions.
You can very likely copy the file [.github/workflows/lifecycle.yml](.github/workflows/lifecycle.yml) to setup our default automation for project management.
