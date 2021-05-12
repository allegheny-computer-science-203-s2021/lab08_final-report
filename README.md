# cs203s2021-lab08: Project 2 Final Report

## DUE: May 18th by midnight (along with the project 2 code repository)

## Table of Contents

* [Summary](#summary)

* [Objectives](#objectives)

* [Code of Conduct](#code-of-conduct)

* [Technical and Professional Skills](#technical-and-professional-skills)

* [Assignment Assessment](#assignment-assessment)

* [System Commands](#system-commands)

  * [Using Docker](#using-docker)
  * [Using Gradle](#using-gradle)
  * [Automated Checks with GatorGrader](#automated-checks-with-gatorgrader)

* [Receiving Assistance](receiving-assistance)

## Summary

Designed for use with [GitHub Classroom](https://classroom.github.com/), this
repository contains the starter for Laboratory 8, corresponding to final report for a Software Project 2, in Computer Science 203. As
part of this assignment, you should answer all of the questions in the
`report.md` file, furnishing evidence of your contributions towards
completing the second software engineering project. Students
who have questions about this task should talk with a student technical leader
or the course instructor. Before the due date for this laboratory assignment,
please ensure that:

- Followed a specific software engineering framework throughout the project.

- Throughout the project, you made significant contributions to the shared GitHub project 2 repository for each week of the second software engineering project, as evidenced by commits to the main branch of the repository that you and your team members merged through the use of the GitHub Flow model.

- The project repository contains appropriate documentation, README badges, continuous integration, automated testing.

- The build status for the shared GitHub repository for the software engineering project is passing. In particular, please ensure that all linting checks, for both the source code and technical writing, and all test cases are passing.

- The GitHub repository for the second software engineering project does not have any resolved issues in it that you could have and/or did already handled.

- The GitHub repository for the second software engineering project has a clear listing of any unresolved issues that you did not solve. There should be evidence that you and your team members have thought about how to address these unresolved issues as part of future work on the project.

- The GitHub repository for second software engineering project has closed issues or merged pull requests for which there is evidence that you made a significant contribution to the task.

- This GitHub repository contains a completed report file. You need to complete the checklist and then make sure that you provide a thorough response to all of the technical writing questions in this file. Please make sure that the contents of your reflection file passes the linting checks that are run in GitHub Actions CI. Please use this file to furnish clear evidence of your contributions to this long-term software engineering project.

- This GitHub repository contains a completed assessment file. Notably, you should copy over the assessment file from the previous week and then finish adding skill self-assessments to that version of the file. You need to write sentences that explain your current level of proficiency for a specific technical or professional skill and then justify why you are making that assessment. All skills should be self-assessed at the completion of this project. Also, please make sure that the contents of your assessment file passes the linting checks that are run in GitHub Actions CI.

- You have followed the Code of Conduct collaboratively established in this course.

## Code of Conduct

Throughout the completion of this software engineering project you must adhere
to the code of conduct that we developed as part of a previous laboratory
assignment.
In addition to reporting any violations of the code of conduct,
please make sure that you attest to the fact that you followed the code of
conduct. That is, make sure you have signed the Code of Conduct document in its repository. Students who think that the software engineering team should revise
some aspect of the code of conduct must use the GitHub issue tracker for that
repository to suggest, discuss, and implement any required changes.

## Technical and Professional Skills

Even though the second software engineering project involves a multiple-week
effort, you are expected to make significant contributions to the project every
week. As a means for documenting your contributions to this project, you should
fully complete the report document and, additionally, annotate the
assessment guide to track your proficiency of the professional and technical skills
in the field of software engineering. For this task, please copy the `assessment.md` file from your previous lab report repository. Then, for each skill category, you should write a couple of sentences reporting
your current level of proficiency and the evidence that you would furnish to support
your assessment. If there is not a description next to one of the assessment
criteria, then the instructor will assume that you are currently working at the
:flushed: level. Please note that you are responsible for documenting your
proficiency of all the technical and professional skills in software engineering by
the completion of this long-term software project. **You are expected to assess yourself
in 100% of the skills before this assignment's due date.**

## Assignment Assessment

The grade that a student receives on this assignment will have the following
components.

- **GitHub Actions CI Build Status [up  to 15%]:**: For lab05 repository associated with this assignment students will receive a checkmark grade if their last before-the-deadline build passes.

- **Mastery of Technical Writing [up  to 30%]:**: Students will also receive a checkmark grade
  when the responses to the  writing questions presented in the
  `reflection.md` reveal a proficiency of both writing skills and technical
  knowledge. To receive a checkmark grade, the submitted writing should have
  correct spelling, grammar, and punctuation in addition to following the rules
  of Markdown and providing  accurate answers.

- **Personal Assessment [up  to 15%]:**: Students will also receive a checkmark grade
  when their personal assessment is appropriately documents in the `assessment.md` file.

- **Level of Contribution [up  to 15%]:**: Students will also receive a checkmark grade
  when their level of contribution indicates active engagement in the process of wrapping up the software engineering project. The engagement should be reported in the
  reflection document located in this repository.

- **Mastery of Technical Knowledge and Skills [up  to 25%]**: Students will also receive a
  checkmark grade when their contributions reveal that they have improved on
  the technical knowledge and skills developed during the completion of
  this assignment. As a part of this grade, the instructor will assess aspects
  of the sprint 3 including, but not limited to, the completion of assigned tasks, the use of effective GitHub issues, use of ZenHub board, correct use of GitHub flow practices, and contributions made to the GatorMiner.

All grades for this project will be reported through a student's gradebook GitHub
repository and the feedback pull request in this repository.

**As explained previously, for this long-term software engineering project, you will also receive a separate letter grade for your overall contributions to the long-term software engineering project. The team as a whole will receive a baseline grade for the project and then your grade may be higher or lower than or equal to the baseline depending on the quality of your contributions, your assessment, and your written report.**

## System Commands

### Using Docker

Once you have installed [Docker Desktop](https://www.docker.com/products/docker-desktop), you can use the following `docker run` command to start `gradle grade` as a containerized application, using the [DockaGator](https://github.com/GatorEducator/dockagator) Docker image available on [DockerHub](https://cloud.docker.com/u/gatoreducator/repository/docker/gatoreducator/dockagator).

```bash
docker run --rm --name dockagator \
  -v "$(pwd)":/project \
  -v "$HOME/.dockagator":/root/.local/share \
  gatoreducator/dockagator
```

The aforementioned command will use `"$(pwd)"` (i.e., the current directory) as the project directory and `"$HOME/.dockagator"` as the cached GatorGrader directory. Please note that both of these directories must exist, although only the project directory must contain something. Generally, the project directory should contain the source code and technical writing of this assignment, as provided to a student through GitHub. Additionally, the cache directory should not contain anything other than directories and programs created by DockaGator, thus ensuring that they are not otherwise overwritten during the completion of the assignment. To ensure that the previous command will work correctly, you should create the cache directory by running the command `mkdir $HOME/.dockagator`.

If you are running your program on a Windows Operating System, you should run the following command instead, replacing the word "user" with the username of your machine:

```bash
docker run --rm --name dockagator -v "%cd%":/project -v "C:\Users\user/.dockagator":/root/.local/share gatoreducator/dockagator
```

Here are some additional commands that you may need to run when using Docker:

- `docker info`: display information about how Docker runs on your workstation
- `docker images`: show the Docker images installed on your workstation
- `docker container list`: list the active images running on your workstation
- `docker system prune`: remove many types of "dangling" components from your workstation
- `docker image prune`: remove all "dangling" docker images from your workstation
- `docker container prune`: remove all stopped docker containers from your workstation
- `docker rmi $(docker images -q) --force`: remove all docker images from your workstation

### Using Gradle

Since the above `docker run` command uses a Docker image that, by default, runs `gradle grade` and then exits the Docker container, you may want to instead run the following command so that you enter an "interactive terminal" that will allow you to repeatedly run commands within the Docker container.

In Linux and Mac OS:

```bash
docker run -it --rm --name dockagator \
  -v "$(pwd)":/project \
  -v "$HOME/.dockagator":/root/.local/share \
  gatoreducator/dockagator /bin/bash
```

In Windows OS (replace `user` with your machine's username):

```bash
docker run -it --rm --name dockagator -v "%cd%":/project -v "C:\Users\user/.dockagator":/root/.local/share gatoreducator/dockagator /bin/bash
```

Once you have typed this command, you can use the [GatorGrader tool](https://github.com/GatorEducator/gatorgrader) in the Docker container by typing the command `gradle grade` in your terminal. Running this command will produce a lot of output that you should carefully inspect. If GatorGrader's output shows that there are no mistakes in the assignment, then your source code and writing are passing all of the automated baseline checks. However, if the output indicates that there are mistakes, then you will need to understand what they are and then try to fix them.

## Automated Checks with GatorGrader

In addition to meeting all of the requirements outlined in the assignment sheet, your submission must pass the following checks that [GatorGrader](https://github.com/GatorEducator/gatorgrader) automatically assesses. If [GatorGrader's](https://github.com/GatorEducator/gatorgrader) automated checks pass correctly, the tool will produce the output similar to the one below.

```
✔  The file assessment.md exists in the  directory
✔  The command output has exactly 0 of the 'TODO' fragment
✔  The file conduct.md exists in the  directory
✔  The report.md in  has at least 500 word(s) in total
✔  The report.md in  has exactly 6 of the 'list' tag
✔  The report.md in  has exactly 17 of the 'heading' tag
✔  The report.md in  has at least 1 of the '![' tag
✔  The repository has at least 3 commit(s)
✔  The file report.md exists in the  directory
✔  The command output has exactly 0 of the 'Add Your Name Here' fragment
✔  The report.md in  has at least 1 of the 'code_block' tag

```

## Receiving Assistance

If you are having trouble completing any part of this project, then please talk
with either the course instructor or a student technical leader during the
lab session. Alternatively, you may ask questions in the Slack workspace for
this course. Finally, you can schedule a meeting during the course instructor's
office hours.
