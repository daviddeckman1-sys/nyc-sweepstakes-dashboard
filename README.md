# NYC Sweepstakes Checklist

The GitHub Pages edition adapts the v0.7 manual queue. It publishes reviewed public sponsor information. The local SQLite database and prior entry history stay on the original device. Checkmarks stay in the browser that recorded them. The dashboard has no entry form or sponsor submission capability.

## Daily discovery

[Daily NYC sweepstakes discovery](https://github.com/daviddeckman1-sys/nyc-sweepstakes-dashboard/actions/workflows/discovery.yml) is scheduled for 9 a.m. Eastern each day. Open a completed run and scroll to its summary for the candidate report, source links when available, and API usage. GitHub may delay runs scheduled on the hour and can disable schedules in public repositories after 60 days of inactivity. [GitHub schedule documentation](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule)

Each scan uses GPT-5.4 Mini and makes one OpenAI API request with a requested limit of two web search tool calls. The key is stored as the `OPENAI_API_KEY` repository secret. The first successful run reported three search tool items and about $0.04 at published rates. Actual cost varies with usage. [OpenAI API pricing](https://developers.openai.com/api/docs/pricing)

## Publishing reviewed listings

Before adding a candidate to the checklist, confirm the sponsor, official rules, deadline and timezone, NYC eligibility, and a free online or email entry route that requires only routine details. Exclude paid postage and routes that require a full address, phone number, birth date, ID, banking information or Social Security number at entry. Confirm the entry limit and sponsor's reset time for daily promotions.

Review both small and large prizes. Keep listing IDs stable so editing a listing preserves its browser checkmarks. The scan writes candidate reports in GitHub Actions. A human updates the public checklist after reviewing the sponsor's rules.
