# CONTRIBUTING

As a contributor, here are the guidelines we would like you...

 - [Code of Conduct](#coc)
 - [Question or Problem?](#question)
 - [Issues and Bugs](#issue)
 - [Feature Requests](#feature)
 - [Submission Guidelines](#submit)
 - [Coding Rules](#rules)
 - [Commit Message Guidelines](#commit)
 - [Change Log](#changelog)
 - [License](#license)

## <a name="coc"></a> Code of Conduct

As contributors and maintainers of the project, we pledge to respect everyone who contributes by posting issues, updating documentation, submitting pull requests, providing feedback in comments, and any other activities.

Communication through any of project's channels (GitLab, Slack, mailing lists, etc.) must be constructive and never resort to personal attacks, trolling, public or private harassment, insults, or other unprofessional conduct.

We promise to extend courtesy and respect to everyone involved in this project regardless of gender, gender identity, sexual orientation, disability, age, race, ethnicity, religion, or level of experience. We expect anyone contributing to the project to do the same.

If any member violates this code of conduct, the maintainers of the project wil take action.

## <a name="question"></a> Got a Question or Problem?

Please, do not open issues for the general support questions as we want to keep JIRA issues for bug reports and feature requests. You've got much better chances of getting your question answered on [StackOverflow](https://stackoverflow.com/).

StackOverflow is a much better place to search for answers since:

- there are thousands of people willing to help on StackOverflow
- questions and answers stay available for public viewing so your question / answer might help someone else
- StackOverflow's voting system assures that the best answers are prominently visible.

To save your and our time we will be systematically closing all the issues that are requests for general support and redirecting people to StackOverflow.

If you would like to chat about the question in real-time, you can reach out via the project Slack channel or Skype.

## <a name="issue"></a> Found an Issue?
If you find a bug in the source code or a mistake in the documentation, you can help us by
[submitting an issue](#submit-issue) to JIRA Repository. Even better, you can [submit a Pull Request](#submit-pr) with a fix.

## <a name="feature"></a> Want a Feature?

You can *request* a new feature by [submitting an issue](#submit-issue) to GitLab Repository. If you would like to *implement* a new feature, please submit an issue with a proposal for your work first, to be sure that we can use it. Please consider what kind of change it is:

* For a **Major Feature**, first open an issue and outline your proposal so that it can be discussed. This will also allow us to better coordinate our efforts, prevent duplication of work, and help you to craft the change so that it is successfully accepted into the project.
* **Small Features** can be crafted and directly [submitted as a Pull Request](#submit-pr).

## <a name="submit"></a> Submission Guidelines

## <a name="submit-issue"></a> Submitting an Issue

Before you submit an issue, please search the issue tracker, maybe an issue for your problem already exists and the discussion might inform you of workarounds readily available.

We want to fix all the issues as soon as possible, but before fixing a bug we need to reproduce and confirm it. Having a reproducible scenario gives us wealth of important information without going back & forth to you with additional questions like:

- version of API used
- 3rd-party libraries and their versions
- and most importantly - a use-case that fails

A minimal reproduce scenario using allows us to quickly confirm a bug (or point out coding problem) as well as confirm that we are fixing the right problem.

We will be insisting on a minimal reproduce scenario in order to save maintainers time and ultimately be able to fix more bugs. Interestingly, from our experience users often find coding problems themselves while preparing a minimal repository. We understand that sometimes it might be hard to extract essentials bits of code from a larger code-base but we really need to isolate the problem before we can fix it.

Unfortunately we are not able to investigate / fix bugs without a minimal reproduction, so if we don't hear back from you we are going to close an issue that don't have enough info to be reproduced.

## <a name="submit-pr"></a> Submitting a Pull Request (PR)

Before you submit your Pull Request (PR) consider the following guidelines:

* Search GitLab pull requests for an open or closed PR that relates to your submission. You don't want to duplicate effort.
* Make your changes in a new git branch:

    ```shell
    git checkout -b feat/my-feature-branch master
    ```
    
    or... 

    ```shell
    git checkout -b fix/my-hotfix-branch master
    ```

* Create your patch, **including appropriate test cases**.
* Follow our [Coding Rules](#rules).
* Run the full Project test suite, as described in the [developer documentation][dev-doc], and ensure that all tests pass.
* Commit your changes using a descriptive commit message that follows our [commit message conventions](#commit). 
Adherence to these conventions is necessary because release notes are automatically generated from these messages.

     ```shell
     git commit -a
     ```
  Note: the optional commit `-a` command line option will automatically "add" and "rm" edited files.

* Push your branch to GitLab:

    ```shell
    git push origin feat/my-feature-branch
    ```
    
    or...

    ```shell
    git push origin fix/my-hotfix-branch
    ```

* In Gitlab, send a pull request to `master`.
* If we suggest changes then:
  * Make the required updates.
  * Re-run the project test suites to ensure tests are still passing.
  * Rebase your branch and force push to your GitLab repository (this will update your Pull Request):

    ```shell
    git rebase master -i
    git push --force-with-lease
    ```

That's it! Thank you for your contribution!

### After your pull request is merged

After your pull request is merged, you can safely delete your branch and pull the changes from the main (upstream) repository:

* Delete the remote branch on GitLab either through the GitLab web UI or your local shell as follows:

    ```shell
    git push origin --delete feat/my-feature-branch
    ```
    
    or...

    ```shell
    git push origin --delete fix/my-hotfix-branch
    ```

* Check out the master branch:

    ```shell
    git checkout master -f
    ```

* Delete the local branch:

    ```shell
    git branch -D feat/my-feature-branch
    ```
    
    or...

    ```shell
    git branch -D fix/my-hotfix-branch
    ```

* Update your master with the latest upstream version:

    ```shell
    git pull --ff upstream master
    ```

## <a name="rules"></a> Coding Rules
To ensure consistency throughout the source code, keep these rules in mind as you are working:

* All features or bug fixes **must be tested** by one or more specs (unit-tests or e2e-tests).
* All public API methods **must be documented**. (Details TBC).
* We follow [Standard JavaScript Style Guide][js-style-guide], but wrap all code at **120 characters**.

## <a name="commit"></a> Commit Message Guidelines

We have very precise rules over how our git commit messages can be formatted.  This leads to **more
readable messages** that are easy to follow when looking through the **project history**.  But also,
we use the git commit messages to **generate the Angular DevKit change log**.

### Commit Message Format
Each commit message consists of a **header** and a **body** __(optional)__. 
The header has a special format that includes a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
<body> (Optional)
```

The **header** is mandatory but the **scope** of the header is optional.

Any line of the commit message cannot be longer 100 characters! This allows the message to be easier
to read on GitLab as well as in various git tools.

### Type
Must be one of the following:

* **arch**: An architecture commit. Usually used at the begining of the project or for adding a missing library.
* **build**: Changes that affect the build system or external dependencies. [2]
* **ci**: Changes to our CI configuration files and scripts. [2]
* **docs**: Documentation only changes. 
* **feat**: A new feature. [1]
* **fix**: A bug fix. [1]
* **refact**: A code change that neither fixes a bug nor adds a feature 
* **release**: A release commit. Must only include version changes. [2]
* **revert**: A git commit revert. The description must include the original commit message. [2]
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc). 
* **test**: Adding missing tests or correcting existing tests. 

<sup>[1] This type MUST have a scope. See the next section for more information.</sup><br/>
<sup>[2] This type MUST NOT have a scope. It only applies to general scripts and tooling.</sup>

#### Revert (*)
If the commit reverts a previous commit, it should begin with `revert: `, followed by the header of the reverted commit. 
In the body it should say: `This reverts commit <hash>.`, where the hash is the SHA of the commit being reverted.

### Scope
The scope should be the name of the npm package affected as perceived by the person reading changelog generated from the commit messages.

The following is the list of supported scopes:

* **lib**
* **util**
* **view**
* **route**
* **config**
* **middleware**
* **service/<service-name>**

### Subject
The subject contains succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize first letter
* be concise and direct
* no dot (.) at the end

### Examples
Examples of valid commit messages:

* `fix(middleware): prevent the flubber from grassing`
* `refact(config): move all JSON classes together`

Examples of invalid commit messages:
* `fix(service/users): add a new XYZ command`

  This is a feature, not a fix.
* `ci(service/users): fix publishing workflow`

  The `ci` type cannot have a scope.

### Body
Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes".
The body should include the motivation for the change and contrast this with previous behavior.

### Footer
The footer should contain any information about **Breaking Changes** and is also the place to reference JIRA issues that this commit **Closes**.

**Breaking Changes** should start with the word `BREAKING CHANGE:` with a space or two newlines. The rest of the commit message is then used for this.

A detailed explanation can be found in this [document][commit-message-format].
