# 03- What is Git

## What is Git

Git is the most popular **Version Control System (VCS)** in the world.

Git records the changed made to our code in a special database called repository. It enable us to look into our project history, and see what changes where made, by whom, when and why. And if we mess something it we can easily revert our project back to an earlier state.

![Git Repository](./images/03-01.png "Git Repository")

## Version Control Systems categories

### Centralized

In a **Centralized** system all team members connect to a central sever to get the latest copy of the code, and to share their changes with others.

![Centralized VCS](./images/03-02.png "Centralized VCS")

Examples:

- Subversion
- Microsoft Team Foundation Server

The problem with a Centralized VCS is the single point of failure, if the server gos offline it is impossible to collaborate, or continue to take snapshots of the code.

### Distributed

In a **Distributed** system each team member as a full copy of the code and repository in ts machine, if the server goes offline they can keep on working

Examples:
- Git
- Mercurial

![Distributed VCS](./images/03-03.png "Distributed VCS")

## Why Git?

Reasons to choose Git
- It is free
- Open Source
- Super Fast
- Scalable

Operations like branching and merging are painful in other VCS.