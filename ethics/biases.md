# Biases

Biases are common in software engineering and it is a developer's ethical responsibility to minimise the effects of these. Biases can creep into requirements gathering, design decisions, implementation, testing, and data collection, leading to systems that are unfair, discriminatory, or harmful. See [General Ethics](general.md).

## Implementation Bias

Implementation bias occurs when a developer's assumptions, preferences, or habits unconsciously influence how they build a system. This can result in features that cater to a narrow set of users, overlooked accessibility needs, or interfaces that work well only for users similar to the developer. Mitigation includes diverse teams, user research, and inclusive design practices.

## Developer-as-user Bias

Developer-as-user bias happens when developers assume that end users think, behave, and have the same technical proficiency as themselves. This leads to interfaces that are unintuitive for non-technical users, poor onboarding experiences, and features that solve problems the developer imagines rather than real user needs. Mitigation includes user testing, personas, and stakeholder involvement.

## Avalability Bias

Where it is easier to remember where something failed a few times instead of the amount it helped. Availability bias skews risk assessment: a developer may over-engineer error handling for a rare edge case while neglecting more frequent failure modes. Mitigation includes data-driven decision-making, checklists, and peer review.

## Algorithm Bias

Algorithms can have biases too. Algorithm bias arises when training data, feature selection, or model design encode systemic prejudices — often reflecting historical inequalities in the data. This can lead to discriminatory outcomes in areas like hiring, lending, and criminal justice. Mitigation includes auditing datasets for representation, testing for disparate impact, transparency in model decisions, and ongoing monitoring after deployment.
