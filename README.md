<div align="center">
<a href="https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow"><img width=800 src="https://github.com/user-attachments/assets/4b6977f4-0e2f-4f61-8eeb-7d30851fe8ad"/></a>


<!--<img width=200 src="https://user-images.githubusercontent.com/67019001/116832951-17b47780-abb7-11eb-9829-588528414ebd.png"/>
<br/><h2>Transfer Issues Labeled With</h2>
<span>Move issues betwen repositories when certain label is used.</span>-->
</div>
<hr/>
<div align="center">

<!-- Badges - Replace projectName with the name of the project also, change or add the link-->

[![Visits](https://visitor-badge.laobi.icu/badge?page_id=Astorcamon.Transfer_Issues_by_Label_Workflow)](https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow)
[![Downloads](https://img.shields.io/github/downloads/Astorcamon/Transfer_Issues_by_Label_Workflow/total)](https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow/releases)
[![License](https://img.shields.io/github/license/Astorcamon/Transfer_Issues_by_Label_Workflow)](https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow/blob/main/LICENSE.md)
[![Latest Release](https://img.shields.io/github/v/release/Astorcamon/Transfer_Issues_by_Label_Workflow)](https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow/releases/latest)
[![Release Date](https://img.shields.io/github/release-date/Astorcamon/Transfer_Issues_by_Label_Workflow)](https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow/releases)

<!-- Tag badges
![Latest Tag](https://img.shields.io/github/v/tag/Astorcamon/Astorcamon)
-->
<!-- Nuget badges
![Nuget Package](https://img.shields.io/nuget/v/:packageName)
![Nuget Package](https://img.shields.io/nuget/dt/:packageName)
-->
<!--Language badges
![Languages](https://img.shields.io/github/languages/count/Astorcamon/Transfer_Issues_by_Label_Workflow)
![Top Language](https://img.shields.io/github/languages/top/Astorcamon/Transfer_Issues_by_Label_Workflow)
![Repo Size](https://img.shields.io/github/repo-size/Astorcamon/Transfer_Issues_by_Label_Workflow)
![Visits](https://badges.pufler.dev/visits/Astorcamon/Transfer_Issues_by_Label_Workflow)
-->
</div>
<!--
## Table of Contents
- [Project Description](#project-description)
- [Getting Started](#getting-started)
- [Support Development](#support-development)
-->
<hr/>
<br/>

<!-- ## Project Description -->
This workflow (action) for GitHub allows you to automatically move issues to the target repository you choose.<br/>
You can assign a label to a type of issue and, when someone applies it, the issue is instantly transferred.<br/>
With this wonderfull tool, you can:
- ✅ Move security-risk issues to a private repository. (See ⇾ 💡)
- ✅ Move multiple issues at once by assigning the label you previously defined. (e.g., “move”, “high”, “risk”…)
- ✅ Send spam issues to a separate repository. (See ⇾ 💡)
- ✅ Set different target repositories for different labels. (See ⇾ 💡)
- ✅ Create a single action per transfer type or group all transfers into one workflow.
- ✅ Use it however you want — it’s extremely versatile!. 👍

<br/>

▶ **Try it** ⇾ *[Send a Security Risk][security-risk-report]*

<br/><hr/>

💡 **Tips:** 
- You can create a [Security Risk template][Issue-template] and define which repository should receive those issues in the workflow.<br/>
When someone reports a risk using that template, the issue will be instantly transferred — like magic. 🧙‍♂️

- To move issues to different repositories, create two or more workflows with different names.

- You can move multiple issues to the assigned repository in a single shot.<br/>
<br/>To do this:
  1. Set the label name and the target repository in the workflow (one‑time setup).
  2. Select and assign the label to the issues you want to move (whenever you need).
  3. When the action finishes, the issues will disappear from the source repository.
- You can quickly clean a repository by recycling it (delete/create) or simply forget it exists… 🤷
- You can also create an action that periodically empties your “recycle bin” repository. 🗑️

<br/>
<hr/>
<br/>

## Getting Started
With this workflow, you can define one or more labels that will be used to transfer issues to another repository.<br/>
The action listens for the “labeled” event and performs the transfer whenever the chosen label is applied.

Some steps are requiered to use this workflow:

1. Create an action with the content of [Transfer_Issues_by_label.yml][Transfer-issues-script]
   - `Go to: Actions > New workflow > Setup a workflow yourself.` Then, replace the content with the script copied.
   - Or download the script and add it to your .github/worflows foler.

2. Create a personal access token (PAT) with repository permissions. *(enable all `"repo"` scopes)*
   - `Go to: User Settings > Developer settings > Personal access tokens > Generate new access token.`<br/>
   - Then copy the token.

3. Create a secret named *ACTIONSYNC* and use the *PAT* created in the previous step.
   - `Go to: Repo Settings > Secrets > New repository secret.`
   - Then paste the token from *step 2*.<br/><br/>
   ℹ *The secret must be created in the source reposotory, where the action runs.*<br/>
   ⚠ *If you arere not the target repository owner, the owner must also create the PAT from *step 2**

4. Create a target repository or use an existing one
   - To use default variables, name the target repository *SourceRepoName_**Private***
   - To use a different reopsitory, change the value of the `TargetRepo` variable
   - If the target will receive confidential issues (e.g, security ristks) set it as **Private**.

5. Adjust the variables in the action created in *step 1* as nedded.
   - In most cases, you only need set `LabelName` to the the label that will trigger the action.<br/><br/>
   ℹ *By default, Variables use the owner and source repository where the action is running.*<br/>
   *The target repository is set to SourceOwnerUsername/SourceRepoName_**Private.***

   - For other scenarios, adjust any variable as needed.

### Variable definitions
- `LabelName` - The name of the label or labels (comma-separated) that triggers the issue transfer.
- `GITHUB_TOKEN` - The personal access token (PAT) or repository secret containing the PAT.
- `SourceOwner` - The owner username of the source repository where the action runs and the issue is taken.
- `SourceRepo` - The source repository where the action runs and the issue is taken.
- `TargetOwner` - The owner username of the target repository where the issue will be sent.
- `TargetRepo` - The target repository where the issue will be sent.

### Technical details
This workflow uses [GitHub - Actions](https://docs.github.com/en/actions) and [GitHub Api - GraphQL](https://docs.github.com/en/graphql)

<br/>
<hr/>
<br/>

## Support Development
<Table>
   <th>Paypal</th>
   <th>Github</th>
   <th>Ko-Fi</th>
  <tr>
    <td><a href="https://www.paypal.com/donate?hosted_button_id=P2C76DEXQEEFQ"><img src="https://img.shields.io/badge/Donate-blue?style=flat&logo=paypal" width="115"/></a></td>
    <td><a href="https://github.com/sponsors/Astorcamon"><img src="https://img.shields.io/badge/Sponsor-404040?style=flat&logo=GitHub-Sponsors" width="135"/></a></td>
    <td><a href="https://ko-fi.com/astorcamon"><img src="https://img.shields.io/badge/Donate-gray?style=flat&logo=kofi" width="128"/></a></td>
  </tr>
</table>

[issue-template]: https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/manually-creating-a-single-issue-template-for-your-repository
[security-risk-report]: https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow/issues/new?assignees=Astorcamon&labels=0+Security+Risk&template=05_security_risk.md&title=
[transfer-issues-script]: https://github.com/Astorcamon/Transfer_Issues_by_Label_Workflow/blob/main/.github/workflows/Transfer_Issues_by_Label.yml
