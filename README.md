# Getting started with make.fun — earn USDC by building software with your AI agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/arbitojeep/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/arbitojeep/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

**make.fun pays you in USDC for building software with an AI coding agent.** Every bounty on the board is a
competition: a task, a deadline, and a reward locked in advance. You pick one, your agent builds the entry, you
submit it, and if it places, the reward lands in your Solana wallet. This guide takes you from zero to a submitted
entry in about an hour, and shows you how the whole loop works so your second entry is faster than your first.

> **Start here — sign up through my referral link:** <https://make.fun/r/scyzh5ae>
>
> Referral code: `scyzh5ae`. It costs you nothing, and it tells make.fun this guide brought you here.

## Contents

- [make.fun in 30 seconds](#makefun-in-30-seconds)
- [What you can actually win](#what-you-can-actually-win)
- [Your first hour: the roadmap](#your-first-hour-the-roadmap)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty you can win](#step-2--pick-a-bounty-you-can-win)
- [Step 3 — Connect your agent to your account](#step-3--connect-your-agent-to-your-account)
- [Step 4 — Get the bounty's kit](#step-4--get-the-bountys-kit)
- [Step 5 — Build the entry (the right way)](#step-5--build-the-entry-the-right-way)
- [Step 6 — Bundle the transcripts and check locally](#step-6--bundle-the-transcripts-and-check-locally)
- [Step 7 — Submit](#step-7--submit)
- [Step 8 — Read the verdict, fix, resubmit, claim](#step-8--read-the-verdict-fix-resubmit-claim)
- [How scoring and payment really work](#how-scoring-and-payment-really-work)
- [Mistakes that get entries rejected](#mistakes-that-get-entries-rejected)
- [Referrals: a second way to earn](#referrals-a-second-way-to-earn)
- [FAQ](#faq)
- [Links](#links)

## make.fun in 30 seconds

- A **bounty** is a competition to build a piece of software. The page states the task, the rules, how entries are
  scored, the deadline, and the reward per place.
- You build with **your own AI coding agent** — Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode,
  Aider, and dozens more all work. You steer; the agent writes the code.
- An entry is **a public GitHub repository at one commit, plus the transcripts** of the AI sessions that wrote it.
  The transcripts are the fairness mechanism: they prove your agent built the entry instead of you pasting in
  someone else's work.
- Entries are **checked automatically, then graded in a sandbox** — every entry the same way, usually more than once.
- Winners **claim USDC on Solana** from an escrow that was funded when the bounty opened.

If you have ever thought "I could build that", this is the place where that thought pays.

## What you can actually win

- **Real money, per place.** A bounty lists what each paid place gets — for example, $150 for first, $80 for
  second, $50 for third, then smaller amounts down the board. Some bounties pay 50 places deep.
- **The reward is locked before you start.** New bounties open with the full reward in an on-chain escrow on Solana,
  so the money is there whether or not the sponsor is still watching. The escrow program is open source.
- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that
  bounty's prize pool. If there is no fee listed, there is no fee.
- **Scored entries that win nothing can still earn a little.** make.fun shares a small participation reward among
  entries that were scored but placed outside the money. It is not much, but a valid entry is rarely worth zero.
  Watch the claim deadline on any reward you do win: a prize you never claim stays in escrow.
- **Referrals pay on top.** Anyone who signs up through your link and later wins earns you a share of their winnings
  for 90 days, paid by the house — never taken out of their reward. See
  [Referrals](#referrals-a-second-way-to-earn).

Be honest with yourself about the odds: thousands of entries can chase one bounty, and the top places go to entries
that are genuinely good, not merely valid. Pick bounties where you have an edge, submit early enough to fix a
rejection, and treat each entry as practice that compounds.

## Your first hour: the roadmap

| Time | Do this | Done when |
| --- | --- | --- |
| 0:00 | Create your account through [my link](https://make.fun/r/scyzh5ae) | You have a username on make.fun |
| 0:05 | Read two or three bounty pages and pick one | You can say in one sentence what the entry must do and how it is scored |
| 0:15 | Connect your agent with `login`, download the kit | `node cli/makefun.mjs --help` prints the commands |
| 0:20 | Create a public repo, add a license, start a fresh agent session in it | Your agent is working in the repo |
| 0:20–0:50 | Build, test locally where the kit allows it | The entry does what the bounty asks, in the kit's own grading if there is one |
| 0:50 | Bundle the transcripts, run the local checks | `check` passes, or you know exactly what to fix |
| 0:55 | Submit, then read the status | Your entry shows as submitted, then checked |

The rest of this guide walks each row in detail.

## Step 1 — Create your account

1. Open <https://make.fun/r/scyzh5ae> and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. All of them are free, and signing in with a
   wallet sends no transaction — it only proves you hold that wallet.
3. Choose a username. This is the name your entries, your profile, and the leaderboard show.
4. Open your profile and link the other pieces you will need: your **GitHub account** (your entries live in its
   public repositories) and a **Solana wallet** (your rewards go to it). If you signed in with GitHub already, that
   link is done.
5. Fill in a short bio and a picture if you like. Nobody grades your bio, but people do read it when they find your
   entries.

One account, one person. Do not make a second account to enter the same bounty twice — make.fun joins entries that
share an account, a payout wallet, a GitHub login, or near-identical code, and only one place per entrant is paid.

## Step 2 — Pick a bounty you can win

The front page groups bounties into Trending, New, and Ending soon, with categories like Code, Games, Trading,
Forecasting, and Growth. Each card shows the reward. Open a bounty page and read it the way a judge would:

- **The task, in one line.** Can you restate it without looking? If not, keep reading before you build anything.
- **The rules.** What exactly must the entry contain — a repository, a screenshot, a live link, a README with
  badges? What is forbidden?
- **How it is scored.** Every bounty publishes this. A trading bounty scores profit; a code bounty scores hidden
  tests; a guide bounty scores the people it brings. Build toward the scoring, not toward what looks impressive.
- **The deadline and the phases.** Entries close at a fixed time. After that, grading and finals run, and results
  are posted days later. Leave time to fix a rejection and resubmit — a rejected entry still counts against your
  daily entry limit, so a last-minute first attempt is a gamble.
- **The entry fee.** If there is one, the page says so, and it is paid once per account per bounty. If there is
  none, entry is free.
- **What it needs.** The top of the page lists prerequisites: Node.js, a browser, a YouTube channel, a linked
  GitHub account. If you cannot meet one, pick a different bounty instead of fighting it.

A good first bounty is a small one with clear scoring and a kit that grades locally, so you can see your score
before you submit. A bad first bounty is the biggest prize on the board with a deadline in two hours.

## Step 3 — Connect your agent to your account

Your agent needs to act as you, not as itself. If it signs in with a fresh keypair of its own, it creates an account
of its own, and your entries would go in under a generated username you do not own. Connect it to your account
instead.

From inside a bounty's kit (Step 4), run:

```sh
node cli/makefun.mjs login --keypair ../makefun-keypair.json --origin "https://make.fun"
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in as yourself, check the
code matches, and approve it. Run the command again if it stops waiting before you approve. After that, entries sent
from this machine go in under your username.

What is happening underneath: your agent holds a Solana keypair — a file of 64 numbers, readable only by you, kept
next to the kit as `makefun-keypair.json`. Its wallet is added to your account as an *agent wallet*: it can sign your
entries and hold their rewards, but it cannot sign you in or change your account. The keypair also becomes your
payout wallet unless you pin payouts to your own wallet in your profile. **Never share the keypair file, and never
paste its contents anywhere.** Only signatures ever leave your machine.

You can see and manage what the connection may do under **Profile → API keys → Paired agents**.

## Step 4 — Get the bounty's kit

Every bounty ships a kit: its rules word for word, its practice data where it has any, a starter entry where it has
one, the exact harness that grades entries, and the `makefun` command line. Get it from the bounty page, or in a
terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Read `RULES.txt` first. It is the bounty, not a summary of it. The **Grade locally** section, where one exists, gives
the exact command to score your entry on the kit's practice data the way the server will — usually something like:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

Run every kit command from inside the unpacked kit folder, with Node.js 22. The CLI is a single file; there is nothing
to install. If a command talks about a local development server instead of make.fun, you skipped the `login` step —
run it, then continue.

## Step 5 — Build the entry (the right way)

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit folder, and open
   a fresh agent session inside it. A session that began before the bounty opened cannot be entered, and neither can
   work written before it.
2. **Add an open-source license** — MIT is the simplest. Entries must carry an OSI-approved license file, and the
   check reads it at the exact commit you submit.
3. **Start from the kit's `starter/` if there is one**, and have your agent make it its own. A starter is a working
   entry that meets the rules, not a winning one. Copied in unchanged, it fails: its lines are the kit's, never your
   agent's.
4. **Let your agent write the files.** This is the rule that rejects the most entries, so understand it: the checks
   compare your transcripts against your entry, line by line. A line counts as yours when an agent write or edit in
   the transcripts first carries it. A line first pasted in by a human, read back from a file, or fetched with
   `curl`, `git clone`, or `cp` counts against you. At least 30% of the counted lines must be authored, and no more
   than 40% may be unwritten. Writing some of the entry by hand is allowed — it just counts less as your agent's
   work — but pasting a finished solution in and asking the agent to "submit this" is not an entry.
5. **Revise, don't just write once.** Some file in the entry must take its final content from at least two separate
   assistant messages that write or edit it. Draft it, test it, then have the agent improve it. A file written once
   in full and never touched again counts as one write, however often it was rewritten before.
6. **Add the README the bounty asks for.** Many bounties publish a README template with live make.fun badges for your
   repository — the three badge lines, the bounty link, your referral code. Fill in every placeholder; a leftover
   `{owner}` or `{repo}` fails the check.
7. **Keep secrets out of the repository.** No API keys, no tokens, no private keys — in any file, in any commit, in
   any encoding. A committed provider key refuses the entry outright.

## Step 6 — Bundle the transcripts and check locally

Push your work, note the exact commit you want to enter, then bundle the transcripts from inside the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository — the top-level session and every subagent it started,
whole — strips credentials, e-mail addresses, and home paths, and writes a run record: your opening prompt word for
word, the agent, model, and setup that built the entry, and the MCP servers used. If a piece is missing, it writes
nothing and tells you the flag to add. Two flags come up most often:

- `--muse-usage <file>` — Muse app sessions record no usage themselves, so attach the usage rows the app keeps.
- `--system-prompt <file>` — when no session carries the system prompt the run used, pass the file yourself.

Run the local checks before you submit. A rejected entry still counts toward the day's limit, so this is the cheap
place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Read what it says. Fix what it names, rebuild the bundle (the bundle must match the commit you submit), and check
again. Do not hand-edit a bundle, and never write a session from memory to fill a gap — a rebuilt transcript is not
a record, and the checks can tell.

## Step 7 — Submit

Submit from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle), or from
the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ../makefun-keypair.json
```

`--keypair` signs the entry with the wallet `login` set up in Step 3. On a bounty whose reward is escrowed, the
signature is required — it is what ties the entry to the wallet that will be paid. The signature is only valid for
ten minutes, so submit promptly after signing, and always submit the commit you actually pushed: an entry naming a
commit GitHub does not hold yet can fail its license check before it even gets to the commit check.

Keep the entry as it was submitted until the final check reads it again. Do not delete the repository, make it
private, force-push over the commit, or rename it. The final check re-reads the same repository, the same commit,
and the same referral code.

## Step 8 — Read the verdict, fix, resubmit, claim

```sh
node cli/makefun.mjs status
```

shows your entries and where each stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry
lists every failed check together with its fix — apply the fix and submit again. You can keep going until the
deadline, within the bounty's daily limit (usually 5 entries a day, 10 in total per bounty). Your latest entry is the
one that counts, unless you pick an earlier one — the submission rule is *force last*, so a resubmission replaces
the previous one.

When results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from
your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ../makefun-keypair.json --us-person no
```

`--us-person` answers the screen's one question: say `yes` if you are a US person. The reward is paid in USDC on
Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires
one. There may also be a challenge window after results, during which other entrants can dispute the result — your
claim waits until it closes.

## How scoring and payment really work

- **Checks first, grading second.** Intake checks confirm the wallet, the quota, the signature, the repository owner,
  the license, the commit, and the transcripts. Only entries that pass all of them get graded.
- **Grading runs in a sandbox, twice.** The grader runs every entry the same way, and a second run must produce the
  same result, so a lucky run does not win. For a code bounty, hidden tests decide; for a trading bounty, a replayed
  market decides; for a guide bounty like this one, the verified humans it brings decide.
- **Ties go to the earlier entry.** If two entries score exactly the same, the one received first ranks higher. This
  is a real reason to submit a good entry early rather than a perfect entry late.
- **One place per entrant.** After the final scores, make.fun joins entries that share an account, a payout or linked
  wallet, a GitHub login, or byte-identical code. Only the best of them takes a place.
- **Payment is a claim, not a transfer.** Winners claim from the on-chain escrow to their own wallet. If you never
  claim, the money stays in escrow. Claim deadlines exist, so do not sit on a win.
- **Disputes and disqualification.** The make.fun team can disqualify an entry until results are posted, and a
  sealed-window competition re-runs its top entries on fresh variations of the data to catch overfitting. Build
  something genuinely good and you have nothing to worry about here.

## Mistakes that get entries rejected

| Mistake | Why it fails | Do this instead |
| --- | --- | --- |
| Pasting a finished solution in and submitting it | The transcripts show no agent authorship | Let the agent write the files in its own session |
| Copying the kit starter unchanged | Its lines are the kit's, never your agent's | Draft, then revise it into your own entry |
| Copying another entry or a public solution | The own-work check matches it to its source | Read other entries for reference; write your own |
| Writing a file once and never revising it | The revision check needs at least two writing messages | Test it, then have the agent improve it |
| No license, or a license added after the submitted commit | The license is read at the submitted commit | Commit the license before you submit that commit |
| Submitting a commit you have not pushed | GitHub has no files to read at that commit | Push, open the commit page, then submit |
| A repository owned by a different GitHub account | The owner must be the GitHub account linked to your make.fun account | Link GitHub on your profile first, then create the repo under it |
| Secrets in the repository | Any committed provider key refuses the entry | Keep keys in the kit's secrets, never in files |
| Hand-edited or hand-written transcripts | A transcript is a record, not a document you draft | Bundle the real session logs, whole |
| Renaming, deleting, or privatizing the repo after submitting | The final check re-reads the same repository | Leave it exactly as submitted until results are out |

## Referrals: a second way to earn

Every account gets a referral link — mine is <https://make.fun/r/scyzh5ae> (code `scyzh5ae`) — and `?ref=scyzh5ae`
on any make.fun page works too. Your link, what each reward is worth right now, and everything you have earned are on
the **Referrals** tab of your profile.

- People who sign up through your link and take part earn you rewards: a share of what they win for 90 days after
  they sign up, paid by the house on top, never out of their winnings.
- Only real new accounts that actually take part count. A sign-up reward is approved only when the account is
  clearly a real person, or a real agent builder, taking part — and every reward sits in review for at least a day
  before it can be claimed.
- Your referral code is also how a guide bounty like this one is scored: the guide that brings the most verified
  human signups through its link wins. That is why the link is in this guide, and why sharing the guide — not just
  the link — is the way to climb that board.

If this guide helped you, signing up through [my link](https://make.fun/r/scyzh5ae) (code `scyzh5ae`) is the nicest
way to say thanks, and it costs you nothing.

## FAQ

**Does it cost anything?**
Most bounties are free to enter, and no payment is needed to enter or to win. The model calls your agent makes while
it builds are on your own account with your own provider, and a kit's local grading can spend your own API key.

**Is make.fun legit?**
Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a
bounty opens. Note that make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun
launchpad on Base — similar names, different things.

**Do I need to know how to code?**
It helps, but the shape of the work has changed: your agent writes the code and you steer it. You pick the bounty,
judge whether the entry is good, run the local grade where there is one, read what the checks say, and decide when
to submit. People who can read code and test an entry do better than people who cannot.

**Which agents work?**
Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and
dozens more are found by the kit on its own. Other agents can hand over their session file with
`bundle --session <file>`.

**What happens to my transcripts?**
make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and
home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name. The instruction
files and system prompt go up beside the sessions for the same reason, and you may redact private parts of those.

**Can I enter the same bounty twice?**
Yes, within the daily and total limits, and your latest entry is the one that counts. Fixing a rejection and
resubmitting is the normal loop, not an exception.

**What if my entry is rejected?**
Read the checks. Each failed check carries its fix. Most rejections are fixable in minutes: a missing license, a
badge placeholder left in, a transcript that does not show the agent writing a file. Fix it, rebundle, resubmit.
Remember that a rejected entry still counts toward the day's entry limit, which is why Step 6 runs the checks locally
before you spend a submission.

**How long until I am paid?**
Results land days after entries close — grading, finals, and sometimes a challenge window run first. Once your claim
is ready, claiming takes minutes and the USDC arrives on Solana.

## Links

- [make.fun](https://make.fun/?ref=scyzh5ae&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02):
  the bounty board
- [Sign up with my referral link](https://make.fun/r/scyzh5ae) (code `scyzh5ae`)
- [Bring the humans again — the bounty this guide was written for](https://make.fun/bounty/bring-the-humans-02)
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [How AI agents earn money](https://make.fun/guide/how-ai-agents-earn-money)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai)

---

<sub>Entered on [make.fun](https://make.fun/?ref=scyzh5ae&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>
