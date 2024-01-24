
# Github FAQs for MEDLab

This is a quick reference page for new MEDLab members. New members of
MEDLab could use this page as a starting point for all project repos for
the lab. The setup assumes the new member has access to MacOS or Unix
machine and uses some terminal commands for setup.

## Prerequisites

1)  [R](https://www.r-project.org) and [Rstudio](https://posit.co)
    installed on the machine.
2)  A [github](https://github.com) account.
3)  Access to the following pages: [UMCSTaR](https://github.com/UMCSTaR)
    and [PLSC](https://github.com/PLSC).

## Setting up ssh keys

1)  Navigate to the github profile settings.

<figure>
<img src="images/github_profile_settings.png"
alt="Fig: github profile settings" />
<figcaption aria-hidden="true">Fig: github profile settings</figcaption>
</figure>

2)  Navigate to ssh and gpg keys

<figure>
<img src="images/ssh_gpg_keys.png" alt="Fig:ssh gpg keys" />
<figcaption aria-hidden="true">Fig:ssh gpg keys</figcaption>
</figure>

3)  Follow steps 1 and 2 at [Generating a new ssh
    key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key)
    to generate ssh keys on your machine. Recommendation: use rsa
    instead of Ed25519 algorithm for legacy systems compatibility.
    Additional note: it is recommended that the email address used in
    the sample command in the previous link matches the email address
    used for the github account.

<figure>
<img src="images/adding_ssh_key.png" alt="Fig:add ssh key" />
<figcaption aria-hidden="true">Fig:add ssh key</figcaption>
</figure>

4)  Copy the output from the following terminal command (the entry
    `id_rsa.pub` depends on the algorithm you used in the previous step)
    and paste it into the ssh entry page highlighted below. You may
    enter a unique identifier in the “Title” field if you would like to
    distinguish between different ssh keys from different machines
    before clicking the “Add SSH key” button.

``` bash
cat .ssh/id_rsa.pub
```

<figure>
<img src="images/ssh_key_entry.png" alt="Fig:ssh key entry" />
<figcaption aria-hidden="true">Fig:ssh key entry</figcaption>
</figure>

## Setting up Rstudio for version control

1)  Initialize Rstudio and access the settings (on Macs: Edit \>
    Settings… \> Git/SVN):

2)  Ensure the “SSH key” entry pointing to the ssh key location you
    generated in the previous section. You can check the ssh key output
    from the previous command matches the ssh key used by RStudio via
    the “View public key” option on the settings panel. ![Fig:RStudio
    settings](images/rstudio_settings.png)

3)  Once you have completed the previous steps, you are ready to clone
    and start working on MEDLab projects stored in the repository.

## Cloning Repos and Pushing Changes

1)  Start by navigating to a project page. An example
    ([github_faq](https://github.com/UMCSTaR/github_faq)) is displayed
    below. Note the green “Code” button highlighted. Copy the ssh entry
    as displayed.

<figure>
<img src="images/sample_github_repo.png"
alt="Fig:sample github repo page" />
<figcaption aria-hidden="true">Fig:sample github repo page</figcaption>
</figure>

2)  Use Rstudio to clone the repo by creating a new project (File \> New
    Project… \> Version Control \> Git \> Create Project). Note in
    \[Fig:step 2c\], you have the option of putting the project in a
    subdirectory on your machine. Use the prompts after the “Browse…”
    button to navigate to the preferred location on your machine. Also
    note that you have the option to name the project on your local
    machine via “Project directory name” field (recommendation:avoid
    using special characters or spaces in this field. eg !, “, etc).
    There is also an option to”Open in new session” if you are working
    on another project while cloning a repo.

<figure>
<img src="images/new_proj_wizard1.png" alt="Fig:step 2a" />
<figcaption aria-hidden="true">Fig:step 2a</figcaption>
</figure>

<figure>
<img src="images/new_proj_wizard2.png" alt="Fig:step 2b" />
<figcaption aria-hidden="true">Fig:step 2b</figcaption>
</figure>

<figure>
<img src="images/new_proj_wizard3.png" alt="Fig:step 2c" />
<figcaption aria-hidden="true">Fig:step 2c</figcaption>
</figure>

3)  After cloning the repo, you can make changes to the local version of
    the repo. After making changes and saving, you will notice that the
    file changed will be highlighted under the git tab of the RStudio ui
    as displayed below.

<figure>
<img src="images/rstudio_git_ui.png" alt="Fig:rstudio git ui" />
<figcaption aria-hidden="true">Fig:rstudio git ui</figcaption>
</figure>

4)  Ensure that the “Staged” check boxes are checked for the changes
    that you intend to commit and push to the repo on github. Note: that
    the status symbols of “A” and “M” denote the file added and modified
    respectively in the changes you are making. After checking the
    “Staged” check boxes, click on the “Commit” button to bring up the
    following window. Enter an informative description of the changes
    you are making to the “Commit message” field. Note that there are
    portions of code highlighted red and green which denote text deleted
    from the version on github and text added relative to the version on
    github respectively. You can use this diffs as reference to annotate
    your commit. Once ready, hit the “Commit” button. A commit
    confirmation window will pop-up. You may close that window. then hit
    the “Push” button to push the commit to the repo. A push
    confirmation window will pop-up. You may close that window. You have
    just pushed changes to the repo on github.

![Fig:rstudio commit-ui](images/commit_message.png) ![Fig:rstudio
commit-confirmation](images/commit_confirm.png)

![Fig:rstudio push-button](images/push_button.png) ![Fig:rstudio
push-confirmation](images/push_confirm.png)

5)  If you are collaborating with collaborators, you can pull changes
    that were made by others to the master branch to the repo via the
    following button on the RStudio ui. Note the two ui elements
    highlighted in the image below: the pull button and the branch you
    are pulling (master branch in the example).

<figure>
<img src="images/pull_button.png" alt="Fig:pull master" />
<figcaption aria-hidden="true">Fig:pull master</figcaption>
</figure>

6)  If you are collaborating on the same branch, it is good practice to
    do a git pull before making any modifications to your project to get
    the latest remote version from the repo and avoid any conflicting
    changes when trying to commit and push aforementioned changes.

7)  If you are collaborating with a large number of collaborators, it
    may be better to use multiple branches within the repo to track
    changes before merging them to the master branch. For further
    details on branches and git, please check out
    [branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)
    and [about
    github](https://docs.github.com/en/get-started/using-git/about-git).

8)  Note that the steps outlined in this page are very RStudio and UI
    centric relative to all the other references due to the nature of
    the work that the lab does. We also did not discuss more obscure
    issues about git such as
    [forking](https://docs.github.com/en/get-started/quickstart/fork-a-repo),
    [resolving
    conflicts](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github),
    etc. Ultimately, one should adopt a workflow that is most conducive
    to one’s style of work.
