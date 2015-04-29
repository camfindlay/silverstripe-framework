# Request for comment (RFC)

## Why RFCs?
This is part of the SilverStripe core decision-making process and addresses the gap between the idea phase and the pull request submission (and merge).

The rationale behind this process is to:
 * Improve visibility on how the decisions made, producing a more open community mood
 * Clarity on what the proposal is, its rationale and impact
 * Reduce unnecessary work when coding large features is done without community and core-committers buy-in
 * Improved likelihood of an optimal solution being merged - the pressure is much higher to approve the change if the coding has already been done (it’s much easier to make adjustments in the design phase)

The important thing to understand about the RFCs is that these are NOT a way to request features. Rather, they are a way to bring clarity so people understand what change is being proposed.

## When to write an RFC?

We intend RFCs to be the primary mechanisms for proposing major new features, for collecting community input on an issue, and for documenting the design decisions that have gone into SilverStripe. The RFC author is responsible for building consensus within the community and documenting dissenting opinions.

Before writing the actual summary RFC document, the idea should have already had a wide range of discussion in various community communication channels. Once discussions reach a point where you think most of the difficulties have been worked through then create the RFC using the template provided.

The benefits of writing an RFC for non-trivial feature proposals are:
 * Obtaining a preliminary approval from core-committers on an architecture before code is completed, to mitigate the risk of a non-merge after a PR is submitted
 * Community becomes aware of incoming changes prior to the implementation
 * RFC can be used as a basis for documentation of the feature
	
## How to write an RFC?
### Template
The following heading can act as a template to starting your RFC.
 * **Introduction** - include a reference #, title, author
 * **Motivation** - why this is a good idea
 * **Proposal** - how you propose to implement the idea after community discussion
 * **Alternatives** - what other approaches were considered during the community discussion phase and why they were not chosen
 * **Impact** - How will this change potentially impact on SilverStripe core? The good and the bad.

###Submitting
Once complete submit the RFC as a GitHub issue, in markdown format and include the ID number of the RFC based on the current list of existing proposals.

## What next?
The RFC will be raised and discussed by the core committers in the monthly Google Hangout sessions, a vote for accepting the RFC will be taken requiring a majority vote (with at least a quorum of more than half of the core committers present).

Once approved this means that if a pull request meeting the idea set out in the RFC was raised that it would be merged (pending the usual code peer review).


## RFC Archive
 RFC # | Proposal | Status
------ |----------|-------
RFC-1  | [Asset abstraction](https://github.com/silverstripe/silverstripe-framework/issues/3792) | Approved
