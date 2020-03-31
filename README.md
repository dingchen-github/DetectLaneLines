# **Finding Lane Lines on the Road**
This is my first project in the Udacity Nanodegree program [Self-Driving Car Engineer](https://www.udacity.com/course/self-driving-car-engineer-nanodegree--nd013), and also my first project using Git and GitHub together!

The original [readme.md](https://github.com/udacity/CarND-LaneLines-P1) is a manual for students; I change it to a documentation of how I got the set-up going.

## Prio to the project
Prio to this project, I took two Udacity free courses [Version Control with Git](https://www.udacity.com/course/version-control-with-git--ud123) and [Writing readmes](https://www.udacity.com/course/writing-readmes--ud777), which were very helpful to me to get to know Git. However, they did not teach students how Git and GitHub work together. I used the search engine to teach myself.

For this project, I did the following set-ups:
* Using `git clone <repository URL>` to get the repo from Udacity GitHub
* On my GitHub, creating a new repo with no initializing, and copying the URL
* Using `git remote set-url origin <repository URL>` to change the origin to my GitHub repo
* Using `git push -u origin master` to upload the repo to my GitHub

*Note: During the course I used Atom, which I find perfect to write readme.md, because I can edit the Markdown text while seeing the preview!*


## Starter-Kit
Udacity provides a [starter-kit](https://github.com/udacity/CarND-LaneLines-P1) to students for a unified environment. When I was following the instructions, I got a problem creating the environment using `conda env create -f environment.yml`. It took a dozen minutes only ending up with no environment (which you can see by trying to activate the environment `source activate carnd-term1`). Thanks to a [question](https://knowledge.udacity.com/questions/55633) in the Udacity Knowledge, I could solve this by putting all entries of "dependencies" under "-pip:" in the environment.yml in the starter-kit folder (see below; additionally, I removed all versions in this .yml as suggested by the answers).

![Screenshot of my environment.yml](https://github.com/dingchen-github/DetectLaneLines/blob/master/yml.png)

## Jupyter notebook

`jupyter notebook`

*Note: The Udacity tutors have made 92 commits. The commits from 93 are from me :)*
