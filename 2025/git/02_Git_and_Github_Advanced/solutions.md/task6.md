# Task 6: Branching Strategies Used in Companies

In real-world companies, the chosen Git branching strategy is a crucial part of collaboration and release management. Here's the breakdown of how they choose them and how they work.

# Git Flow:

Branches : 

- main : production-ready code . 
- develop: integration branch of features.
- feature/*: new feature
- release/*: preparing new versions .
- hotfix/*: urgent fixes on production. 

Where used: 

- Enterprises
- Products with long release cycle .

Why: 

- clear separation of work 
- works well with planned releases. 

Challenges : 

- can become complex . 
- overhead of managing many branches . 

# GitHub Flow:

Branches:

- main: always deployable.
- short-lived feature branches .

Workflow: 

- create feature branch 
- push commits 
- open pull requests(PRs)
- review and merge into main 
- deploy from main branch 

Where used: 

- startups 
- SaaS products 
- team doing continous deployment 

Why:

- simple and fast
- Encourages frequent deployments 

Challenges:

- not ideal for complex release management .

# GitLab Flow: 

Combines: 

- feature branches . 
- environment branches (e.g.staging , production)
- optional release branches 

Where used : 

- teams using DevOps pipelines 
- companies needing both CI/CD and release control. 

Why : 

- flexible 
- works well with environment based deployment . 

# Trunk-Based Development:

Principle:

- Developers work directly on main branch or on very short-lived branches . 
- Feature plags hide incomplete features .

Where used: 

- High-speed dev team.
- Companies practicing continous integration/deployment .

Why:

- Encourages rapid integration.
- Reduces merge conflicts 
- Simplifies history 

Challenges: 

- Requires excellent automated testing .
- Harder for big risky changes , without feature flags . 

# Release Branching :

Approach :

- Create branches like : release/1.0, release/2.0
- Bug fixes get cherry-picked into relevant releases. 

Where used: 

- Companies maintaining long-term version like softwares , libraries. 

Why: 

- supports multiple production versions .
- Help manages patches and backports . 

Challenge:

- complex backports 
- maintenance burden 

# Companies choosing their branching strategies :

Team Size : 

- Small Size then they use simple flow like GitHub flow , Trunk-based flow 
- Large Size then they use structured flow like Git flow, Release branches. 

Release Frequency:

- Frequent releases occurs they use simpler flow 
- Long release cycles they use more structured branching .

Product Type :

- For Web apps they use GitHub flow 
- Libraries , SDKs they use release branches . 

Tooling : 

- DevOps pipelines for GitHub flow or trunk-based branching .

Risk Tolerance: 

- High-speed teams they use trunk-based technique
- Safety-critical software they use release branches , stricter flow .

Therefore , Companies pick the branching strategy that balances speed, safety, and simplicity for their product and team size . 
