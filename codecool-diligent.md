# Diligent

## Table of Contents

- [Git](#git)
- [Agile Methodologies](#agile-methodologies)

## Git ___ [Background material](./diligent-background-material/GIT%20version%20control%20system.pdf)

### Git Commands

- Basic commands:

  - `git init`: Create a new repository

    - Initializes an empty Git repository in your current directory, allowing version control.

  - `git clone`: Clone an existing repository 

    - Copies an existing repository (from a URL) to your local machine.

  - `git add`: Add files to the staging area

    - Moves changes from the working directory to the staging area, preparing them to be committed.

  - `git commit -m "message"`: Commit changes with "message" commit message

    - Records changes from the staging area in the repository with a descriptive commit message.

  - `git status`: Check the repository status

    - Shows the current state of your working directory and staging area, including modified and untracked files.

  - `git log`: View commit history
    - Displays a list of previous commits along with details such as author, date, and commit message.

- Additional commands

  - `git push`: Push local changes to the remote repository

    - Uploads local commits to a remote repository like GitHub or GitLab.

  - `git pull`: Download remote changes and merge them into local code

    - Fetches the latest changes from the remote repository and merges them into your local branch.

  - `git fetch`: Download remote changes (without merging)
    - Retrieves the latest changes from the remote repository but does not merge them, allowing you to inspect the changes first.

- Branches:

  - `git branch new-feature`: Create "new-feature" branch

    - Creates a new branch called "new-feature" from the current branch.

  - `git checkout -b new-feature`: Also create "new-feature" branch

    - Creates and switches to the new "new-feature" branch in a single command.

  - `git checkout new-feature`: Switch to "new-feature" branch

    - Changes the working directory to the "new-feature" branch.

  - Merge:

    - `git checkout master`: Switch to "master" branch

      - Switches your working directory to the "master" branch.
      - Git uses a three-way merge to automatically combine changes by comparing your branch, the other branch, and their common ancestor. A merge conflict happens when both branches modify the same line or when one branch deletes something the other modifies. In such cases, Git requires manual conflict resolution before completing the merge.

    - `git merge new-feature`: Merge "new-feature" branch into "master"
      - Integrates changes from the "new-feature" branch into the "master" branch.

- Special commands:

  - `git revert`: Reverse the effect of a commit

    - Creates a new commit that undoes the changes made by a specific previous commit, without altering the commit history.

  - `git cherry-pick`: Copy a single commit to another branch
    - Copies a specific commit from one branch to another, without merging the entire branch.

## Agile Methodologies ___ [Background material](./diligent-background-material/agile_methodologies.md)


### Waterfall Methodology

- **The history of the waterfall methodology is presented.**
  - The waterfall model originated in manufacturing and construction industries, and was first adapted to software development by Dr. Winston W. Royce in 1970.
- **The history of the waterfall methodology in software development is presented.**
  - It was introduced as a linear and sequential approach to software development, where each phase must be completed before the next begins.
- **The different stages of the waterfall methodology are explained.**
  - The stages include Requirements, Design, Implementation, Verification, and Maintenance, flowing in one direction like a waterfall.
- **Three disadvantages of the waterfall methodology are presented.**
  - Limited flexibility, difficulty in accommodating changes, and higher risk of discovering issues late in the process.
- **Two examples of sectors where the waterfall methodology is being used are shown.**
  - Construction and manufacturing sectors, where strict regulations and clear documentation are essential for project success.

### Kanban Methodology

- **The history of the kanban methodology is presented.**
  - Kanban originated in Toyota’s manufacturing system in the 1940s to manage inventory and improve efficiency.
- **The history of the kanban methodology in software development is presented.**
  - In the late 2000s, Kanban was adapted for software development to enhance project flow and flexibility, focusing on continuous delivery.
- **The kanban cards and the kanban board are briefly explained.**
  - Kanban cards represent tasks, and the kanban board is a visual tool that shows workflow stages, helping teams track task progress.
- **Three benefits of using the kanban methodology are presented.**
  - Improved visibility of workflow, reduced bottlenecks, and flexibility in adapting to changes.
- **Two examples of sectors where the kanban methodology is being used are shown.**
  - Software development and IT support teams, as well as retail inventory management.

### SCRUM Roles

- **The three SCRUM roles are mentioned.**
  - Product Owner, SCRUM Master, and Development Team.
- **The responsibilities of each SCRUM role are explained in detail.**
  - Product Owner defines the project vision and backlog; SCRUM Master facilitates the process and removes blockers; Development Team executes the work.
- **Three benefits of using the SCRUM methodology are explained.**
  - Greater team collaboration, faster delivery through sprints, and adaptability to changes.
- **A reason why using SCRUM could be beneficial in a company is provided.**
  - SCRUM allows teams to be more responsive to customer feedback and rapidly changing project requirements.

### SCRUM Ceremonies

- **The five different SCRUM ceremonies are mentioned.**
  - Sprint Planning, Daily Stand-up, Sprint Review, Sprint Retrospective, and Backlog Refinement.
- **Each SCRUM ceremony is explained in detail.**
  - Sprint Planning defines tasks for the upcoming sprint;
  - Daily Stand-up checks progress;
  - Sprint Review showcases work done;
  - Sprint Retrospective identifies improvements;
  - Backlog Refinement prepares future work.
- **An explanation of which one SCRUM ceremony could be removed to improve it is presented.**
  - Daily Stand-ups are sometimes unnecessary because they can take up too much time, especially in small teams or when there's little progress to report.
  - Some teams might find Backlog Refinement redundant if the product backlog is already well-defined.
- **An explanation of which one SCRUM ceremony could be added to improve it is presented.**
  - A team bonding session could be added to build better rapport and improve team dynamics.

### SCRUM User Stories

- **The given concept is explained.**
  - A user story is a short, simple description of a feature or requirement from the perspective of the end user.
- **The concept of estimation points is explained.**
  - Estimation points quantify the effort required for a user story, often using the Fibonacci sequence for sizing.
- **One example of a point estimation system for SCRUM user stories is presented.**
  - Planning Poker is a popular system where team members assign points based on complexity.
- **The SCRUM user story template is explained.**
  - A common template is: "As a [user], I want [goal] so that [reason]."
- **One example of a SCRUM story template is presented.**
  - "As a customer, I want to receive notifications so that I stay updated on order status."
- **The SCRUM acceptance criteria is explained.**
  - Acceptance criteria are conditions that must be met for the story to be marked as complete.
- **One example of an acceptance criteria for the previous user story template is presented.**
  - Notifications must be sent via email and SMS, and include order status and delivery date.

### SCRUM Board

- **The given concept is explained.**
  - A SCRUM board visualizes tasks for the sprint and helps track their progress from "To Do" to "Done."
- **A suggestion for five column names for a SCRUM board is provided.**
  - To Do, In Progress, Code Review, Testing, Done.
- **An explanation of how to move and organize stories in a SCRUM board is provided.**
  - Stories move across columns as work progresses, starting from To Do and advancing through each stage until Done.
- **The term SCRUM sprint is explained.**
  - A sprint is a time-boxed iteration (usually 1-4 weeks) where specific tasks are completed.
- **The term SCRUM velocity is explained.**
  - Velocity is the measure of work completed during a sprint, helping teams estimate future work capacity.
- **Some benefits of using a board to organize tasks are presented.**
  - Visual tracking improves team collaboration, makes progress visible, and identifies bottlenecks early.
