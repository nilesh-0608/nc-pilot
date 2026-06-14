# LinkedIn Find & Apply — profile

This skill uses the SAME saved info as Find Jobs (the search) and Easy Apply (form filling).
Put these into **Options → Your info / context**. The more you fill, the less it has to ask.

> The final Submit of every application always needs your explicit "yes" in chat.

## Search

- `targetJobTitle`:          <!-- main role, e.g. Full Stack Engineer -->
- `titleKeywords`:           <!-- comma-separated alternates -->
- `locationFilter`:          <!-- city / Remote / country -->
- `excludeKeywords`:         <!-- skip titles containing these -->
- `easyApplyOnly`:           <!-- yes = only Easy Apply listings -->
- `maxApplications`:         <!-- safety cap per run -->

## Identity & form filling (same as Easy Apply)

- `firstName`, `lastName`, `email`, `phoneCountryCode`, `mobileNumber`, `location`, `city`
- `workAuthorization`, `requiresSponsorship`, `noticePeriod`, `willingToRelocate`, `preferredWorkType`
- `totalYearsExperience`, per-skill `yearsExperience`, `highestEducation`, `linkedinUrl`
- `screeningAnswers`: exact question → answer pairs for repeat screening questions

## Notes for the agent

<!-- e.g. always confirm before submit (default), companies to avoid, tone for free-text answers. -->
