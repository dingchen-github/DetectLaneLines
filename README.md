# **Finding Lane Lines on the Road**
This is my first project in the Udacity Nanodegree program [Self-Driving Car Engineer](https://www.udacity.com/course/self-driving-car-engineer-nanodegree--nd013), and also my first project using Git and GitHub together!

The original [readme.md](https://github.com/udacity/CarND-LaneLines-P1) is a manual for students; I change it to a documentation of how I got the set-ups going. If any student would have difficulties gettig started, and happend to find my readme.md, I hope she or he could find my experience useful.

*Note: My thoughts on the implementation of the project are written in [writeup_template.md](https://github.com/dingchen-github/DetectLaneLines/blob/master/writeup_template.md).*

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

Then I tried to run `jupyter notebook`, but the terminal said that this command did not exist. I thought Jupyter notebook is automatically installed within Miniconda; it turned out that I needed to install it myself. So I ran `conda install -c conda-forge notebook` to get the notebook. Then it worked!

## Python modules

So I opened the code file and tried to import Python modules. Again, an error message... No modules were found. OK, let me get the modules in Miniconda:
- `conda install matplotlib` which also got numpy for me.
- `conda install -c menpo opencv3`, again, error message. My Python version is too high for opencv3.
- Wait a minute, opencv's latest version is 4.2.0, why am I installing opencv3? On the [conda-forge](https://anaconda.org/conda-forge/opencv) website I found the command to install 4.2.0: `conda install -c conda-forge opencv`
- `conda install -c conda-forge moviepy` on the [conda-forge moviepy 1.0.1](https://anaconda.org/conda-forge/moviepy) site

Now I can import all modules without an error message.

## Image functions

The function *image reading* returned an error saying: "ValueError: Only know how to handle extensions: ['png']; with Pillow installed matplotlib can handle more images". Yep, it cannot handle the jpg files. Hey, since I have opencv, why not just use `cv2.imread`? It worked!

The function *image showing* returned an error saying: "TypeError: Image data of dtype object cannot be converted to float". Again, I have opencv, so I tried `cv2.imshow`. I had to use `cv2.waitKey(0)` and `cv2.destroyAllWindows()` together to get the image, otherwise the window just freezed and I hat to restart Jupyter notebook.

The function *image writing* only worked, after the folder was created manually.

## Summary

It was not easy at all to got all set-ups correct. As a newcomer I encounted the above problems and had to do a lot of search to find solutions. But I am very glad that I have overcome all kinds of trouble!

*Note: The Udacity tutors have made 92 commits. The commits from 93 are from me :)*
