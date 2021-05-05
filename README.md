<!--Template repository to create new repositories.
Fill the content whith any you want.-->

<div align="center">
<img width=800 src="https://user-images.githubusercontent.com/67019001/116883513-fb9bef00-ac25-11eb-9db2-86d2fdaf0e68.png"/>
<!--<img width=200 src="https://user-images.githubusercontent.com/67019001/116832951-17b47780-abb7-11eb-9829-588528414ebd.png"/>
<br/><h2>Transfer Issues Labeled With</h2>
<span>Move issues betwen repositories when certain label is used.</span>-->
</div>
<hr/>
<div align="center">
   
<!-- Badges - Replace projectName with the name of the project also, change or add the link-->

![Downloads](https://img.shields.io/github/downloads/Astorcamon/Transfer_Issues_by_Label_Workflow/total)
![License](https://img.shields.io/github/license/Astorcamon/Transfer_Issues_by_Label_Workflow)
![Latest Release](https://img.shields.io/github/v/release/Astorcamon/Transfer_Issues_by_Label_Workflow)
![Release Date](https://img.shields.io/github/release-date/Astorcamon/Transfer_Issues_by_Label_Workflow)
<!-- Tag badges
![Latest Tag](https://img.shields.io/github/v/tag/Astorcamon/Astorcamon)
-->
<!-- Nuget badges
![Nuget Package](https://img.shields.io/nuget/v/:packageName)
![Nuget Package](https://img.shields.io/nuget/dt/:packageName)
-->
![Languages](https://img.shields.io/github/languages/count/Astorcamon/Transfer_Issues_by_Label_Workflow)
![Top Language](https://img.shields.io/github/languages/top/Astorcamon/Transfer_Issues_by_Label_Workflow)
![Repo Size](https://img.shields.io/github/repo-size/Astorcamon/Transfer_Issues_by_Label_Workflow)
![Visits](https://badges.pufler.dev/visits/Astorcamon/Transfer_Issues_by_Label_Workflow)

</div>

## Table of Contents
- [Project Description](#project-description)
- [Getting Started](#getting-started)
- [Support Development](#support-development)

<br/>
<hr/>
<br/>

# Project Description
This workflow (action) for GitHub allows you automatically transfer issues to another repository when you applies a label previously defined.
- ✅ You can use this to move issues that are a security risk to a private repository. (See => 💡)
- ✅ You also can select multiple issues and assign the label "move", to transfer several issues to another repository. 
- ✅ You can use it to move spam to a separate repository. (See => 💡)
- ✅ You can set diferent target repos for diferent labels.
- ✅ You can create an action for every transference or movement you need or group all in one action.
- ✅ Use it as it suits you. It's a lot versatile!. 👍😉

💡 **TIP** - *You can create an [issue template][Issue-template] labeled by default as security risk and a private repo as target of this type of issues. 
<br/>When someone reports a risk using the template, the issue will be automatically moved to the private repository you assigned to.*

▶ **Try it** => *[Send a Security Risk][security-risk-report]*

💡 **TIP** - *You can select multiple issues and asign the label spam for sending it to a spam repository.
<br/>When you want, you can easily clean this repo by recycling (delete / create it).
<br/>You also may create an action that periodically do this for you or just do a clean up by removing all issues.*

⚠ **IMPORTANT** - *By unknown reasons, any previously existing label on the issue will be removed during the process.*

### Credits
***This project is an encapsulation of the great work of:** [octokit/graphql-action](https://github.com/octokit/graphql-action)
<br/>Combined with [GitHub - Actions](https://docs.github.com/en/actions) and [GitHub Api - GraphQL](https://docs.github.com/en/graphql)*

<br/>
<hr/>
<br/>

# Getting Started
With this script, you would be able to set a label that will be used to transfer issues to another repository.
<br/>When the action is listening the event "labeled" and you set the right label to one or more issues, the event is triggered and the action transfers the issue(s) to the repo you set as target of this type of issues.

Some steps are requiered to use this workflow:

1. Create an action with the content of the script => [Transfer_Issues_by_label.yml][Transfer-issues-script]
   - `Go to: Actions > New workflow > Setup a workflow yourself.` Then, replace the content with the script copied.

1. Create a personal access token (PAT) with repo access permissions. *(Check all repo permissions)*
   - `Go to: User Settings > Developer settings > Personal access tokens > Generate new access token.` Then, copy the token.

1. Create a secret with name *ACTIONSYNC* and the PAT created before.
<br/><br/>ℹ - *Must be at the source repo, where the action is running.*
<br/>⚠ - *If you are not the target repo owner, the target owner must create the same token PAT. (step 2)*
   - `Go to: Repo Settings > Secrets > New repository secret.` Then, paste the token copied at step 2.

1. Create a repo as target or use an existing one
   - If you want to use the variables by default, name the target repo like *SourceRepoName**Private***
   - If you want to use an existing one, change the value of the variable `TargetRepo`.
   - If you want to send confidential data to the target, like security risks, set this repo as **Private**.

1. Change the variables for the action created at step 1 as your convenience.
   - For most cases, just need to change LabelName for the name of the label you want to use for triggering the action.
<br/><br/>ℹ - *Any other variables are set by default with the owner and source repo where the action is running and the target repo as SourceOwner/SourceRepoName**Private.***

   - For different scenarios, change any variable at your convenience.

### Variable definitions
 `LabelName` - The name of the label that triggers the action to transfer the issue.
<br/> `GITHUB_TOKEN` - Personal access token (PAT) or repo secret with PAT. 
<br/> `SourceOwner` - The source repository owner where the action is running and the issue will be moved from.
<br/> `SourceRepo` - The source repository where the action is running and the issue will be moved from.
<br/> `TargetOwner` - The target repository owner where the issue will be moved to.
<br/> `TargetRepo` - The target repository where the issue will be moved to.

<br/>
<hr/>
<br/>

# Support Development
**If you find useful [my work](https://github.com/Astorcamon), please, consider to support development.** 😉

*You may also add me to your credits for more diffusion:* `![Astorcamon](https://github.com/Astorcamon)`

**Thank you so much** 😊

<Table>
   <th>Paypal</th>
   <th>Github</th>
  <tr>
    <td><a href="https://www.paypal.com/donate?hosted_button_id=P2C76DEXQEEFQ"><img src="https://img.shields.io/badge/Donate-blue?style=flat&logo=paypal" width="115"/></a></td>
    <td><a href="https://github.com/sponsors/Astorcamon"><img src="https://img.shields.io/badge/Sponsor-404040?style=flat&logo=GitHub-Sponsors" width="125"/></a></td>    
  </tr>
</table>

[issue-template]: https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/manually-creating-a-single-issue-template-for-your-repository
[security-risk-report]: https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow/issues/new?assignees=Astorcamon&labels=0+Security+Risk&template=05_security_risk.md&title=
[transfer-issues-script]: https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow/blob/main/.github/workflows/Transfer_Issues_by_Label.yml
