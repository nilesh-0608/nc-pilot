# LinkedIn Easy Apply — user profile (source of truth)

The profile data the Easy Apply agent fills forms from. Field names match the
`system_prompt.md` profile object exactly. Fill in your real values; leave a field blank or
delete it if not applicable. For a blank/missing field the agent will **draft a proposed
answer from your other data and ask you to confirm** before using it — it never silently
invents or submits an unconfirmed answer. The more you fill in, the less it has to ask.

> Stored locally with the extension. Do NOT put sensitive data here (government IDs,
> bank/financial numbers, passwords) — the agent is instructed to refuse those and let you
> fill them personally. The final Submit always requires your explicit confirmation.

## Identity

- `firstName`:
- `lastName`:
- `email`:
- `phoneCountryCode`:        <!-- e.g. +91 -->
- `mobileNumber`:
- `location`:                <!-- full "City, Country" as LinkedIn shows it -->
- `city`:

## Resume

- `resumeFileName`:          <!-- exact name of the resume already uploaded to LinkedIn to select -->

## Work authorization

- `workAuthorization`:       <!-- e.g. Citizen / Permanent resident / Work permit -->
- `requiresSponsorship`:     <!-- yes / no -->

## Availability & preferences

- `noticePeriod`:            <!-- e.g. Immediate / 2 weeks / 1 month -->
- `currentLocation`:
- `willingToRelocate`:       <!-- yes / no -->
- `preferredWorkType`:       <!-- remote / hybrid / onsite -->

## Compensation

- `currentCTC`:
- `expectedCTC`:

## Years of experience (per skill)

<!-- One line per skill. Agent maps "How many years of X?" to these. -->

- `yearsExperience`:
  - React: 
  - Node.js: 
  - <skill>: 

## Background facts (for multiple-choice screening questions)

<!-- LinkedIn Easy Apply often asks dropdown/radio questions. Provide your real values so the
     agent picks the matching option instead of guessing. -->

- `totalYearsExperience`:        <!-- total professional years, e.g. 4 -->
- `yearsInCurrentCompany`:       <!-- e.g. 2 -->
- `lastOrgIndustry`:             <!-- e.g. SaaS / Fintech / E-commerce -->
- `lastOrgSize`:                 <!-- e.g. 1-10 / 11-50 / 51-200 / 201-500 / 500+ -->
- `currentRoleCapacity`:         <!-- e.g. Individual contributor / Team lead / Manager -->
- `highestEducation`:            <!-- e.g. B.E. Computer Science -->
- `linkedinUrl`:                 <!-- your full profile URL, asked verbatim sometimes -->
- `preferredWorkSetup`:          <!-- Remote / Hybrid / Onsite -->
- `biggestMotivation`:           <!-- e.g. Growth & learning / Compensation / Impact -->

## Experience summary (for free-text screening questions)

<!-- A few sentences the agent can draw from to answer open questions truthfully instead of
     inventing. Keep it factual — this is your real background. -->

- `currentOrgFocus`:             <!-- "Briefly describe the focus of your current/last org" -->
- `topKpis`:                     <!-- "Top 3 KPIs from your last two roles" — list 3 -->
- `problemSolved`:               <!-- "Describe a problem you contributed to solving" -->
- `interestReason`:              <!-- "Why are you interested in this role?" -->

## Predefined screening answers (exact question → answer)

<!-- For questions you've seen before, pin an exact answer. The agent matches the question
     text and uses your answer verbatim; it only fills what matches. -->

- `screeningAnswers`:
  - "Have you ever heard about <company> before applying?": 
  - "Have you applied to <company> for a role before?": 
  - "Are you willing to undergo a background check?": 
  - "Do you have a degree in <field>?": 
  - "<paste an exact question here>": 

## Job selection

<!-- Answers the agent's standard openers so it doesn't have to ask:
     1) which job to apply to, 2) whether it must be Easy Apply.
     Leave a field blank to be asked instead. -->

- `targetJobTitle`:          <!-- e.g. Full Stack Engineer -->
- `targetCompany`:           <!-- e.g. Nivi Capital — blank = any company matching the title -->
- `titleKeywords`:           <!-- comma-separated; match listings containing any of these -->
- `excludeKeywords`:         <!-- skip listings containing these (e.g. Senior, Lead, Intern) -->
- `locationFilter`:          <!-- e.g. Remote / Bengaluru / India -->
- `easyApplyOnly`:           <!-- yes = only apply to listings with the Easy Apply badge; skip external Apply -->
- `onMultipleMatches`:       <!-- ask / pick-first / pick-most-recent -->
- `maxApplications`:         <!-- safety cap per run; default 1 -->

## Notes for the agent

<!-- Rounding preference for fractional years (default: round down), tone for free-text
     answers, questions to always leave for manual review, what NOT to disclose. -->

- Round fractional years: down
