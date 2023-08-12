[[Getting Started with Branches using Git Commands]]
[[Git pull request flow]]
[[GitHub Integrator]]
[[GitHub Repository Administrator]]
1. **git clone** (clone from upstream to prime the local repository)
2. **git pull / git fetch** from 'origin' to keep up-to-date with the upstream
3. **git push** to shared repository
4. **git format** patch to prepare e-mail submission
5. **git send email** to send your e-mail submission without corruption by your MUA
6. **git request pull** to create a summary of changes for your upstream to pull

## Git Workflow
-   Branches are used to isolate changes to code. When the changes are complete, they can be merged back into the main branch.
    

-   Repositories can be cloned to make it possible to work locally, then sync changes back to the original.
    

-   Repositories can be forked to be used as a base for a new project, or so that the developer can work independently.
    
-   A Pull Request (PR) can be submitted to have your changes reviewed and merged.
    
-   Large projects include people working in different roles:
    
-   Developer – creates code
    
-   Integrator – manages changes made by developers
    
-   Repository Administrator – configures and maintains access to the repository