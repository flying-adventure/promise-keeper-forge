# Promise Keeper privacy policy

Last updated: 21 November 2026

Promise Keeper is an app for Jira Service Management, built on Atlassian Forge. It keeps a ledger of the contact promises agents make to customers in public replies ("I'll update you by tomorrow 3pm") and tracks whether each one was kept. This policy explains what the app stores, what it reads, and where the data stays.

## What Promise Keeper stores

For each promise it finds in an agent's public reply, Promise Keeper stores:

- the sentence that contains the promise (at most 500 characters) and the time expression in it, for example "tomorrow 3pm";
- the ID and key of the request, the ID and key of its service project, and the ID of the reply;
- when the reply was written and last edited;
- the deadline the app worked out, the rule it used, and the name of the time zone it used to read the time (for example `America/New_York`). This can be the time zone of the agent who wrote the reply;
- the promise's status (open, kept, kept late, broken or dismissed), when and by which reply it was settled, and whether a reminder note was posted;
- whether the reply was written by the person who raised the request (yes or no, not who).

For every public agent reply, it also stores a small marker: the request ID, the reply ID, the time of the reply, and whether the reporter wrote it. It does not store the text of those replies.

It also stores the app's settings (the default time zone), a summary of the last automatic check (counts only), the ID of its own Jira field, the time it started keeping the ledger, and short-lived retry markers (a request ID) for requests whose field could not be updated yet.

Promise Keeper does not store Atlassian account IDs, names, email addresses or any other identifier of agents or customers. A promise sentence is copied from a reply that was already sent to the customer, so if an agent wrote a name inside that sentence, the name is stored with it.

## What Promise Keeper writes to your site

- The **Promised update by** field on a request: the earliest deadline the customer is still waiting for. Only the app can change this field.
- An **internal note** on a request about one hour before a promise is due. Internal notes are visible to agents only, never to customers.
- **Sample requests**, only when someone clicks **Create sample requests**. They are raised by that person, in the project they chose, with public replies written in that person's name.

## Where it is stored

Everything is stored in Forge hosted storage, inside Atlassian's cloud, separately for each site where the app is installed. Promise Keeper has no servers of its own. It sends no data to any service outside Atlassian and requests no permission to do so. It does not use analytics, tracking or advertising services.

Promises are found and tracked with fixed rules, not AI models, so the same reply always gives the same result. The optional Promise Keeper agent runs in Atlassian Rovo, under your organization's Rovo settings, and uses the app's actions to list promises and to set a deadline after the person in the chat confirms it.

## What Promise Keeper reads

To find and settle promises, it reads the comments on service project requests (the text, whether a comment is public, the author's account type and Jira time zone, and when it was written), the request's reporter, and the request's status and resolution time. It reads them through the Jira and Jira Service Management REST APIs, keeps only what is listed above, and discards the rest.

To show the ledger, it checks which requests the person using the app is allowed to see and whether they can edit a request. It uses the time zone of the person viewing the page to show times and to read promises in that person's own replies.

## Who can see the ledger

People see promises only on requests they are allowed to view: in the request panel, on the project's **Promises** page, and through the Promise Keeper Rovo agent. Dismissing a promise or setting a deadline requires permission to edit the request. Only Jira administrators can change the default time zone.

## Retention and deletion

A promise stays in the ledger until its request is deleted or the app is uninstalled. When a request is deleted, the app deletes that request's promises and markers. When the app is uninstalled, its stored data is removed according to Atlassian's Forge data retention rules.

## Changes

Changes to this policy are published in this file. The history of the file shows what changed.

## Contact

Questions and requests: open an issue at https://github.com/flying-adventure/promise-keeper-forge/issues
