# NYC Sweepstakes Checklist

The GitHub Pages edition adapts the v0.7 manual queue. It publishes only reviewed public sponsor information. The local SQLite database and prior entry history stay on the original device. Checkmarks in this edition are scoped to the current browser. The dashboard has no entry form or sponsor submission capability.

## Daily discovery plan

Discovery is off. Enable it after the repository owner approves the API cost and saves a project API key in GitHub under **Settings → Secrets and variables → Actions** as `OPENAI_API_KEY`. Keep the key out of site files, commits and logs.

Use the following schedule in a GitHub Actions workflow on the default branch after approval.

```yaml
on:
  schedule:
    - cron: "0 9 * * *"
      timezone: "America/New_York"
```

GitHub can delay scheduled jobs, particularly on the hour. For a public repository, inactivity can disable scheduled workflows. See [GitHub's schedule documentation](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule).

1. Have the scheduled job call the OpenAI Responses API with web search to find current small and large prizes with a free online or email entry route for NYC residents. Limit the number of tool calls and output tokens, and record usage without logging credentials. At two search calls per day, 30 days costs about $0.60 for search calls, plus model tokens. Price the model and token limits before enabling the job. See [OpenAI API pricing](https://developers.openai.com/api/docs/pricing).
2. Keep candidates in a review report separate from the site. Require a trustworthy sponsor, finalized official rules, explicit NYC eligibility or coverage that includes NYC, a no-purchase route without paid postage, entry fields limited to routine details, an exact deadline with timezone and the sponsor's entry limit. Exclude routes that require a full address, phone number, birth date, ID, banking details or Social Security number at entry.
3. Publish only after a human checks the rules and entry route. Keep the last reviewed list when discovery fails. Keep listing IDs stable so publishing a refresh preserves browser checkmarks. Store no entrant data in GitHub or OpenAI.
