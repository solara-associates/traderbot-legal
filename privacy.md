---
title: TraderBot privacy notice
---

# TraderBot privacy notice

Last updated 3 October 2026

This notice explains what personal data TraderBot collects, why, where it is kept,
who else sees it, and what happens when you ask us to delete it. It describes what
the software actually does, including the places where deletion is not complete.

## 1. Who is responsible for your data

The controller is **Solara Associates Ltd**, registered in England and Wales,
company number **17479688**. Gecko Labs is a brand of Solara Associates Ltd, and
TraderBot is operated under it.

- Registered office: Lytchett House, 13 Freeland Park, Wareham Road, Poole, Dorset, BH16 6FA
- Contact for any question or request about your data: **info@solara.associates**
- ICO registration: **registration in progress**

We handle your data under the UK GDPR and the Data Protection Act 2018. You can
complain to us and to the Information Commissioner's Office at ico.org.uk at any time.

## 2. What TraderBot is

TraderBot is **paper trading only**. Orders are simulated against a practice account
funded with notional money. No real money is involved, we do not hold client money,
and we do not take payment details.

**Nothing in TraderBot is financial advice.** The assistant explains data when you ask
it to. It cannot place an order, and it offers no view on what you should do.

## 3. What we collect

**When you sign up:** your email address, a password, and the risk tolerance and
investment goal you pick. A first and last name are optional and you can leave them
blank. The password itself is never stored, only a bcrypt hash of it, which cannot be
read back as your password. We record the date and time you accepted this notice and
the terms.

**Automatically, on every request:** your IP address, your browser user agent string,
the time, the path, the response status, how long it took, and your account identifier
once you are signed in. The load balancer in front of the service logs the same request
metadata independently.

**Every sign-in attempt, successful or not:** a security record containing the date and
time, your IP address, your browser user agent, the outcome, and a keyed one-way
pseudonym of the email address that was typed. The address itself is not stored in that
record. Section 8 explains why these records outlive a deletion request.

**As you use it:** your conversations with the assistant, which means the messages you
write, its replies, and conversation titles generated from the first 80 characters of
your first message. Also your simulated orders and positions, your portfolio values,
your watchlist, saved strategies and backtest results, your loss limits and position
size settings, your notification preferences, and any trading rules and trading
philosophy you write. Those last two are free text, so whatever you type is stored as
you typed it.

**If you link your own brokerage account:** the API key and secret you supply, stored
encrypted. This is optional and off by default.

We do not ask for your postal address, phone number, date of birth, national insurance
number, or any payment or card details. Nothing in TraderBot charges you.

## 4. Why we collect it, and our lawful basis

- **To give you the account and features you asked for.** Basis: performance of a contract with you.
- **To keep the service secure and working**, which covers rate limiting, investigating
  abuse, and keeping a tamper evident record of security events. Basis: our legitimate
  interests in protecting the service and its users, and in being able to reconstruct
  what happened after a security incident.
- **To answer you if you exercise a data protection right**, and to show that we did.
  Basis: our legal obligation.

We do not use your data for advertising or profiling, we do not sell it, and we do not
use your messages to train any model of our own.

## 5. Who else sees it

**Anthropic** processes your chat so the assistant can answer. What leaves us is the
conversation itself and your risk tolerance and investment goal settings. Your name,
your email address and your account identifier are not sent. Anything you type into a
message is sent, so a message containing personal details contains them because you
wrote them there.

**Alpaca** runs the simulated orders. What leaves us is the order: ticker symbol,
quantity, buy or sell, order type and any limit or stop price. No personal data goes
with it, and the connection uses our own practice keys, not anything of yours, unless
you have linked your own brokerage keys.

**Market and news data providers**, namely Yahoo Finance, Marketaux, Polygon, Alpha
Vantage and Finnhub, receive ticker symbols and date ranges from our servers. They
receive no personal data, and your browser does not contact them directly.

**Google Cloud** hosts the service, the database and the logs on our behalf.

There is no advertising network, no analytics or tracking in TraderBot, no third party
cookies and no tracking pixels. We do not send you email or SMS: there is no email
provider connected to TraderBot, which also means we cannot currently send you a
password reset.

## 6. Cookies and browser storage

TraderBot sets **no cookies**. It stores three items in your browser's local storage:

- `traderbot-auth`: your session token and the profile returned when you signed in,
  which is what keeps you signed in.
- `traderbot-theme`: whether you chose light or dark.
- `traderbot-onboarding`: how far through the welcome steps you got.

All three stay on your device, are readable only by this site, and are removed if you
clear site data for traderbotapp.com. None is used for tracking. That is why you see no
cookie banner.

## 7. Where it is stored, and for how long

Everything we hold lives in Google Cloud in **europe-west2 (London)**. The database is
PostgreSQL with no public internet address, reachable only from our own private network.

Your chat is processed by Anthropic outside the UK, in the United States. The transfer
relies on the **EU Standard Contractual Clauses, Module Two (controller to processor),
together with the International Data Transfer Addendum to those clauses issued by the
Information Commissioner**, both incorporated by Anthropic's Data Processing Addendum.

| What | How long we keep it |
|---|---|
| Your account, settings, chat history and simulated trading records | While your account exists. An account inactive for 24 months is deleted |
| Security and sign-in records | 12 months |
| Application and load balancer request logs, including IP addresses | 30 days |
| Database backups | The 7 most recent nightly backups |
| Session tokens you have signed out of | Until the token would have expired anyway, then deleted automatically |

## 8. Your rights, and what deletion really does

You have the right to ask for a copy of your data, to have it corrected, to have it
erased, to restrict or object to how we use it, and to receive it in a portable form.
To use any of them, email **info@solara.associates**. We will reply within one month.

Asking us to erase your account **deletes**: your chat history and every message in it,
your simulated orders, positions and portfolio history, your saved strategies and
backtest results, your watchlist, the trading rules and trading philosophy you wrote,
any brokerage API keys you had stored, and your autonomous trading log. It also
overwrites every personal field on your account record, including your email address and
any name, clears your password so the account cannot be signed in to, and ends your
session immediately.

**What survives, and why.** Your sign-in and security records are kept. Each one holds
the date and time, the IP address, the browser user agent, the outcome, and a keyed
one-way pseudonym of the address used, but not the address itself. This is deliberate.
Those records are the audit trail: they are stored append only, and the application can
add to them and read them but cannot change or delete them. That restriction is what
makes the trail worth having, because it means nobody can quietly edit the record of a
security event afterwards, including us. The cost of that property is that an erasure
request cannot reach into it. We keep these records for 12 months in our legitimate
interest in the security and integrity of the service.

Two further things are true and worth saying plainly. **Backups** taken before your
request still contain the old values until they age out, which takes up to 7 nightly
cycles. **Request logs** already written still contain your IP address until they age
out after 30 days.

Deleting our copy of a brokerage API key does not revoke that key at your broker. Only
you can do that, and you should.

## 9. How we protect it

Passwords are stored as bcrypt hashes. Traffic is encrypted in transit. The database has
no public address. Brokerage keys you supply are encrypted before storage. Signing out
revokes your session token, and a deactivated account is refused on every route. Sign-up
and sign-in are rate limited. Security events are written to an append only audit trail.

## 10. Automated decisions

The assistant analyses market data and explains it. It never places an order, every
trade is simulated, and no decision it makes has a legal or financial effect on you. You
are not subject to automated decision making in the sense the UK GDPR means it.

## 11. Children

TraderBot is not intended for anyone under 18 and we do not knowingly collect data about
children. If you believe a child has created an account, email **info@solara.associates**
and we will remove it.

## 12. Changes to this notice

If we change what we collect or what we do with it, we will update this page and the date
at the top. Where a change matters, we will say so in the product.

---

Solara Associates Ltd, company number 17479688. Gecko Labs is a brand of Solara
Associates Ltd. TraderBot is paper trading only and nothing in it is financial advice.
