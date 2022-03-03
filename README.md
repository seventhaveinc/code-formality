# Seventh Ave test

## Company official languages
- JS
- TypeScript
- Golang
- Ruby/Crystal
- Solidity

## Style Guides
1. Official JS Style Guide: JavaScript Semi-Standard, and TS Semi Standard
2. Official GoLang Style Guide: Uber GoLang Style Guide
3. Official Ruby Style Guide: The Ruby Style Guide
4. Official Crystal Style Guide: Crystal Lang Official Coding Style
5. Official Solidity Style Guide: 0xcert Solidity Style Guide

## Work submission guidlines
1. Step 1 Clone Repo locally and make a feature branch that coinsides with your jira ticket
2. If no Jira Ticket exists, create one and tag Your Flight Pilot and Head of Engineering
3. branch should be named as follows for ticket `NC-99` , `feature/NC-99`
4. When that particular ticket is complete make a pull request to your repos `development` branch
5. The peer-reviewer assigned must review within 1 business day
6. Peer reviewer will verify any tests pass, they understand the code, and it meets the appropriate style guide
7. Flight Pilot or Head of Engineering will ensure that the repo satisfies the ask in the Jira ticket
8. Head of Product will ensure that the ticket accomplishes what was intended
9. Every week whatever is in the Development Branches must be tested and either merged to main or a reason must be given why they cannot be
10. Each week each Flight will demo it's progress

## Additional Tools 
1. Pull Request will use the official Seventh Ave Pull Request Template 

```markdown
### Is this PR for a specific JIRA task? If yes, what’s the JIRA task ID?
- [ ] Yes. (*Leave this unchecked if your answer is: No.*)
<!--- Provide the exact ID of your task here (e.g., "SC-50"). -->

### Does your code compile/build without errors?
- [ ] Yes. (*Leave this unchecked if your answer is: No.*)

### Did you merge the master/develop branch into your branch?
- [ ] Master
- [ ] Develop
(*Leave this unchecked if your answer is: No.*)

### Are your changes/updates visual? If yes, insert a screenshot/GIF/video of your changes/updates.
- [ ] Yes. (*Leave this unchecked if your answer is: No.*)
<!--- Insert a screenshot/GIF/video of your changes/updates here. -->
```

2. JS Repos will use `husky`, `commitlint`, `@commitlint/config-conventional` and `lint-staged`
3. This will ensure all commits meet guidelines
4. All APIs must be documented with either `Docco`, `Swagger` or `JSDoc`
5. All Readme's must have up to date information about starting app.
6. The master doc site that will go live next week will be the source of truth for all practices of Engineering (Built with Gatsby) 

