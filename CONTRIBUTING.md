
# Contributing to this repository

First of all, thanks for taking the time to read this document and contributing to our codebase.

## Contributing Checklist

* [ ] Ticket created with details of the change
* [ ] Ticket has the  [team name], Contributing label, and a risk label
* [ ] Contacted [team name] to discuss the change
* [ ] Ticket is refined and feature toggle has been considered
* [ ] Ticket has gone through three Amigos including someone from [team name]
* [ ] Branched from main with appropriate branch name
* [ ] Code completed with unit test coverage
* [ ] Reviewed by your team
* [ ] Tested by your QA
* [ ] Reviewed by [team name]
* [ ] Merged and Released
* [ ] Cleanup feature toggles if required

## Getting started

> Before you begin work on the ticket, reach out to the team so we are aware of the ticket and can answer any questions.
> 
> Jump into the [[team name]](link to team channel) channel and give us a shout, or find us in the office and have the conversation face to face!

The other thing you will need before you start is a ticket describing what it is that you're set to do, or if it's a bug make sure there are clear reproduction steps on the description.

If your team doesn't have access to the ticketing system, we'll create the ticket for you.

Things to talk about in our first conversation:

* Planned implementation
* Feature toggle approach
* Test plan
* Q&A

## Before starting the implementation

* The ticket should be refined, planned and discussed with your team
  * Assign to `[team name]` 
  * Add the `Contribution` label
  * A risk label should be added, either `risk_amber` or `risk_red`
  * Arrange a 3 amigos session including a Tester from your team to fill out the test plan accordingly 
  * If possible, invite a Tester/Engineer from our team since the conversation should only last 10/15 minutes and they will have a better understanding of the context around their own repo

> ### Assessing Risk
> 
> We assess the risk level of a change for all of our tickets, for contributed changes the asserted risk would be either amber, for any typical changes such as adding a small feature, cosmetic changes, or copy changes, or the risk will be red, for large features or any changes where there is a significant risk to the functioning of the page. Note contributed changes will never be green.
> 
> Ensure the risk level is added to the ticket as a label.

### Monitoring and Performance

If your feature adds new API calls or has the potential to impact the performance of the application we will discuss additional steps that are required such as adding logging, updating our dashboards and alerts, or scheduling a performance test before the code is released.

## Working on your feature

### Branching

Our default branch is `main`.

When creating a branch use `main` as the base, ensure the ticket number is included, and leave a meaningful description, eg. `feature/ticket-number-short-description`

### Feature toggles

The preferred approach for new features is to wrap them in a feature toggle instead of making the changes directly. This is evaluated on a case by case basis, we probably would have talked about this in our initial discussion.

### Unit tests

All the tests, coverage and linting are run at build time on our pipeline, so before opening a PR, please run the following command to make sure your branch will pass all the tests:

```console
yarn ci
```

### Coding style

Generally try to match the style and conventions of the code around your changes. Ultimately we want code that is clear, concise, consistent and easy to read.

Broadly we're in-tune with the following style guides:

* JavaScript
  * <https://github.com/prettier/prettier>
  * <https://github.com/airbnb/javascript>
  * <https://github.com/ryanmcdermott/clean-code-javascript>
* React
  * <https://github.com/airbnb/javascript/tree/master/react>
* CSS
  * <https://github.com/airbnb/css>

## Opening a PR

> When a PR is opened, it should be reviewed and tested by your team before being reviewed by [team name]

When development work is done, open a PR against `main` on this repo.  Please make sure you fill the PR template correctly, stating the ticket, writing a descriptive changelog and filling in the checkboxes.  Please also add a label here with the risk level, `Amber Risk` or `Red Risk`.

One engineer from your team should review the changes before testing starts.

### Testing Activities

> Your team is responsible for testing the new code

The code should be tested against the test plan that was created before implementation. The functional and visual tests should be updated for changes, or new tests added for new features.

### Final Approval

Once the code has been reviewed by at least one member of your team, and tested by your QA, mention in the [team name]  channel and ask for a review from [team name].

## Merging and deploying

> [team name] will handle merging and deployment.  Let us know if the branch needs to be deployed for E2E testing.

When the code is fully approved and tested it can be merged, which will be done by [team name] allowing us to manage our priorities.  Once merged it will be deployed to production with our next release.

If you have requirements for testing the new code in an End to End environment, contact the team and let them know so we can arrange this.

We will inform you once the code is deployed.  If the code is behind a feature flag you can then activate it as needed.

## Feature Toggle Removal

> If the new code becomes permanent, remove the feature logic

If the code was wrapped in feature logic, and it is no longer required after an experimental period, then you should remove the feature logic.  Please raise a new ticket and follow these guidelines again.