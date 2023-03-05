# [Deploying GitHub Projects with Vercel](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#)

Vercel for GitHub automatically deploys your GitHub projects with [Vercel](https://vercel.com/), providing [Preview Deployment URLs](https://vercel.com/docs/concepts/deployments/preview-deployments#preview-urls), and automatic [Custom Domain](https://vercel.com/docs/concepts/projects/custom-domains) updates.

## [Supported GitHub Products](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#supported-github-products)

-   [GitHub Free](https://github.com/pricing)
-   [GitHub Team](https://github.com/pricing)
-   [GitHub Enterprise Cloud](https://docs.github.com/en/get-started/learning-about-github/githubs-products#github-enterprise)
-   [GitHub Enterprise Server](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#using-github-actions)

## [Deploying a GitHub Repository](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#deploying-a-github-repository)

## [Changing the GitHub Repository of a Project](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#changing-the-github-repository-of-a-project)

If you'd like to connect your Vercel Project to a different GitHub repository or disconnect it, you can do so from the  [Git section](https://vercel.com/docs/v2/platform/projects#git)  in the Project Settings.

## [A Deployment for Each Push](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#a-deployment-for-each-push)

Vercel for GitHub will  deploy every push by default. This includes pushes and pull requests made to branches. This allows those working within the repository to preview changes made before they are pushed to production.

With each new push, if Vercel is already building a previous commit, the current build will be canceled to build the most recent commit so that you always have the latest changes deployed as quickly as possible.

## [Updating the Production Domain](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#updating-the-production-domain)

If  [Custom Domains](https://vercel.com/docs/concepts/projects/custom-domains)  are set from a project domains dashboard, pushes and merges to the  [Production Branch](https://vercel.com/docs/concepts/deployments/git#production-branch)  (commonly "main") will be made live to those domains with the latest deployment made with a push.

If you decide to revert a commit that has already been deployed to production, the previous  [Production Deployment](https://vercel.com/docs/concepts/deployments/environments#production)  from a commit will automatically be made available at the  [Custom Domain](https://vercel.com/docs/concepts/projects/custom-domains)  instantly; providing you with instant rollbacks.

## [Preview URLs for the Latest Changes for Each Pull Request](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#preview-urls-for-the-latest-changes-for-each-pull-request)

The latest push to any pull request will automatically be made available at a unique  [preview URL](https://vercel.com/docs/concepts/deployments/preview-deployments#preview-urls)  based on the project name, branch, and team or username. These URLs will be provided through a comment on each pull request. Vercel also supports Comments on preview deployments made from PRs on GitHub.  [Learn more about Comments on preview deployments in GitHub here](https://vercel.com/docs/concepts/deployments/preview-deployments#github-integration).

## [Deployment Authorizations for Forks](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#deployment-authorizations-for-forks)

If you receive a pull request from a fork of your repository that includes a change to the  [`vercel.json`](https://vercel.com/docs/cli)  file or the Project has  [Environment Variables](https://vercel.com/docs/concepts/projects/environment-variables), Vercel will require authorization from you or a  [Team Member](https://vercel.com/docs/teams-and-accounts/team-members-and-roles)  to deploy the pull request.

This behavior protects you from leaking sensitive Project information.

You can disable  [Git Fork Protection](https://vercel.com/docs/concepts/projects/overview#git-fork-protection)  in the Security section of your Project Settings.

Vercel for GitHub uses the deployment API to bring you an extended user interface both in GitHub, when showing deployments, and Slack, if you have notifications setup using the  [Slack GitHub app](https://slack.github.com/).

You will see all of your deployments, production or preview, from within GitHub on its own page. See this page for example:  [https://github.com/vercel/vercel/deployments](https://github.com/vercel/vercel/deployments)

Due to using GitHub's Deployments API, you will also be able to integrate with other services through  [GitHub's checks](https://help.github.com/en/articles/about-status-checks). Vercel will provide the deployment URL to the checks that require it, for example; to a testing suite such as  [Checkly](https://checklyhq.com/docs/cicd/github/).

## [Configuring for GitHub](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#configuring-for-github)

To configure the Vercel for GitHub integration, see  [the configuration reference for Git](https://vercel.com/docs/concepts/projects/project-configuration/git-configuration).

You may want to use different workflows and APIs based on Git information. To support this, the following  [System Environment Variables](https://vercel.com/docs/concepts/projects/environment-variables#system-environment-variables)  are exposed to your Deployments:

| Name | Description |
| ----------- | ----------- |
| `VERCEL_GIT_PROVIDER` | The Git Provider the deployment is triggered from. In the case of Git|
|`VERCEL_GIT_REPO_SLUG`|The origin repository of the app on GitHub.  Example:  `my-site`.|
|`VERCEL_GIT_REPO_OWNER`|The GitHub organization that owns the repository the deployment is triggered from.  Example:  `acme`.
|`VERCEL_GIT_REPO_ID`|The ID of the GitHub repository the deployment is triggered from.  Example:  `117716146`.
|`VERCEL_GIT_COMMIT_REF`|The GitHub branch that the deployment was made from.  Example:  `improve-about-page`.
|`VERCEL_GIT_COMMIT_SHA`|The GitHub  [SHA](https://help.github.com/articles/github-glossary/#commit)  of the commit the deployment was triggered by.  Example:  `fa1eade47b73733d6312d5abfad33ce9e4068081`.
|`VERCEL_GIT_COMMIT_MESSAGE`|The message attached to the GitHub commit the deployment was triggered by.  Example:  `Update about page`.
|`VERCEL_GIT_COMMIT_AUTHOR_LOGIN`|The GitHub username belonging to the author of the commit that the project was deployed by.  Example:  `johndoe`.
|`VERCEL_GIT_COMMIT_AUTHOR_NAME`|The GitHub name belonging to the author of the commit that the project was deployed by.  Example:  `John Doe`.
|`VERCEL_GIT_PULL_REQUEST_ID`|The GitHub pull request id the deployment was triggered by. If a deployment is created on a branch before a pull request is made, this value will be an empty string.  Example:  `23`.


Vercel require some permissions through our Vercel for GitHub integration. Below are listed the permissions required and a description for what they are used for.

## [Repository Permissions](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#repository-permissions)

Repository permissions allows Vercel to interact with repositories belonging to or associated with (if permitted) the connected account.

|  Permission |Read |Write | Description|
|---------|-----------|----------|-------- |
|`Administration`|Y|Y|Allows us to create repositories on the user's behalf.
|`Checks`|Y|Y|Allows us to add checks against source code on push.
|`Contents`|Y|Y|Allows us to fetch and write source code for new project templates for the connected user or organization.
|`Deployments`|Y|Y|Allows us to synchronize deployment status between GitHub and the  Vercel  infrastructure.
|`Pull Requests`|Y|Y|Allows us create deployments for each Pull Request (PR) and comment on those PR's with status updates.
|`Issues`|Y|Y|Allows us to interact with Pull Requests as with the  `Pull Requests`  permissions due to GitHub requiring both for access.
|`Metadata`|Y|N|Allows us to read basic repository metadata to provide a detailed dashboard.
|`Web Hooks`|Y|Y|Allows us to react to various GitHub events.
|`Commit Statuses`|Y|Y|Allows us to synchronize commit status between GitHub and  Vercel.

## [Organization Permissions](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#organization-permissions)

Organization permissions allow Vercel to offer an enhanced experience through information about the connected organization.
|  Permission |Read |Write | Description|
|---------|-----------|----------|-------- |
|`Members`|Y|N|Allows us to offer a better team onboarding experience.

### [User Permissions](https://vercel.com/docs/concepts/deployments/git/vercel-for-github#user-permissions)

User permissions allow us to offer an enhanced experience through information about the connected user.

|  Permission |Read |Write | Description|
|---------|-----------|----------|-------- |
|`Email addresses`|Y|N|Allows us to associate an email with a GitHub account.

> ***Note:** Vercel use the permissions above in order to provide you with the best possible deployment experience).*

<br>
<br>

---
### Vercel Documentation
 
>[Vercel Documentations ](https://vercel.com/docs)
