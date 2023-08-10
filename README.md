# Github_tutorial

This tutorial is here to help OpenClassrooms students from the Pole Data discord server to make their first steps with Git and GitHub. I will take the example of an analysis made in a Jupyter notebook (running with Anaconda). The analysis will be very simple to focus on the Git/GitHub work.

# 0-Introduction

I will use Jupyter on Anaconda Navigator:

![image](assets_images/image_1.png)


I also have an account on github and created a new empty repository, with just an empty ReadMe file.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/5c623ec8-1216-45b5-9607-18447f0de59c)

# 1-Setup our project folder

I want to work on a new branch created from this GitHub repository, where I will work on this notebook.
First, I need to create a new branch.
To do this, I will use the Terminal in my Jupyter session (more practical than using the notebook cells, I prefer putting code only in them).

- From the localhost tree tab, I click on "New - Terminal":
  
![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/188830ca-10dd-4c99-b87b-8cdcbe5d4ccf)

- Then, a new tab with my terminal appears.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/c3afac03-4d06-4852-b668-950177e850ab)

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/4dd9fee8-35cd-4ec2-bf77-83715c73207a)


- I check that git is correctly installed:

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/b891b0e7-3eef-4e77-9a82-bf2b8cf4113d)


- Otherwise, if git is not installed yet, I can install it on Windows through this link : https://gitforwindows.org/ or use the command "conda install -c anaconda git" (https://anaconda.org/anaconda/git) to install it as a conda package (both can coexist without conflicts).

- I move into my "Documents" folder and create a new folder for this project using command line in the terminal.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/f650f5d9-b605-41a2-8b61-c87892bc5f5c)


- Do not forget to move into this newly created folder

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/ae69ff95-2467-4d5b-ab0c-cf7fb7e56bcf)


- I want to init here a git repository in this folder using the "git init" command

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/246f94ed-50e6-4a8c-8898-ac8a3e132d53)


An empty git repository is not initialized in my folder.

- We need to configure the user.email and user.name according to the email address and username used on Github (my email address is hidden here):

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/e21a0570-2d4e-4908-a1ed-c5e93710fcff)


- Finally, we need to clone locally our project folder. We can do it using https address:

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/f62bda99-1e51-428e-b9db-3222eac5aad6)


We can copy the https address directly (step 3 on the screenshot).

Then, using the command "git clone" followed by the copied address in the terminal, we clone this github repository locally in our folder.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/0182ce46-aa1d-4291-b147-0d9838020c64)


- We can see that this created a new folder named after the name of the github repository.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/97119f35-41e8-489f-807b-731a8068da2b)


- If we move in this repository, we can see our readme file (this is the only file present in our github repository).

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/d547e30b-c273-4691-9126-a84908f9229d)


We are now ready to work on our code !

# 3- Work on our notebook in a new branch

Imagine we want to work on our notebook and store it on github. We need to create a new branch (good practice, instead of pushing it directly on the master branch).

- I create a new branch named "new_notebook_branch". It is a good practice to create a new branch for each new feature we want to add on our code, but it also depends on different people habits and company habits if you work in a company.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/19398e5a-75b4-4d5e-806e-c595c6ea66f8)



- You can see that there our "main" branch (where the stable and working code is) and you new_feature branch. When in this branch, all the modifications you make locally AND push will be independent from the main branch. This means that people can work on their own branch and push code on their own branch without disturbing you, and also that the main branch can be updated with new code without disturbing you.


- With Anaconda window, I navigate to the git repository I just cloned in my "Documents/OC_git_tutorial_project/" folder:

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/2c2d6e06-e6ef-4cf9-b0f1-ba0302fcc1c8)


- You can see that our locally cloned repository is here with our ReadMe file! I create a new notebook here.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/c65b64c9-fae1-40b7-b1f8-f01748c074cd)


- I work on my notebook and I am happy with my first lines of code. I want to push it on my branch before continuing working, so I know that a "checkpoint" (my commit) will allow me to return to this point later if I need to. I recommend the following worflow:
    - First, "git status" allows to see which files have been modified and can be added to staging area.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/281f7a9a-5543-4c57-9685-fc89ac413d06)


As you can see, I have:
- a .gitignore file in which I wrote the relative path to the original dataset folder, so every file in this folder will not be pushed on github (but we can still have it locally). It is interesting to push this file so other people that will work on the data can have the same project arborescence and put their input files in the same folder.
- a notebook checkpoint folder that it is not necessary to push
- my project notebook "Heart_Attack_prediction_example_project.ipynb" that has the first lines of code and that I want to push
- the 'input_data' folder that contains the csv input file that will not be pushed.

    - Then, "git add" the files we want to add to staging area followed by "git status" to see which files were added to staging area.
    
![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/7e31a75b-10df-4fda-b98e-97d1edf46db6)


We can see in green the files that are in the staging area, ready to be pushed to the branch after commiting.

    - Then, "git commit -m "description of commit" " to commit the staged files. Always use a clear and short commit description, it will be useful in case you want to come back to it later.
    
![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/33159624-ac54-4b8f-8b9c-d77a35d2f702)


We can see our commit description and which files are added in the commit.

- Finally, we can push on our branch using "git push origin branch_name". 

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/5f5defd4-0c0e-4183-9a74-cd3ca10033ae)


We now can open a pull request on our github repository with our project branch by following the indicated URL.
It is highly recommended to write a description of the PR (objective and more technical aspects such as which files are added and what they contain).

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/e41dbcc1-eca3-4e1e-b0ae-da36daefc539)


You have now your first pull request that is opened. You can see that there is no restriction to merge it on the main branch. In companies, you will certainly have rules that your code must follow to be safely added to the main branch.
This is the "Conversation" tab where the commits appear with the PR description. Comments done by pairs on your code will appear here (after they review your code).

You can visualize which files you changed in the "Files changed" tab:

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/f7ba7250-3852-40df-b1e5-9d0ca3f922a2)


You can see in green in the .gitignore file the line that has been added. If you modify a file that existed prior to your branch creation and remove some code or lines in files, they will appear in red with a little "-" indicating that your modifications include code/lines removal.
Large files modifications such as the notebook here are too large to display directly. You can always see the html output by clicking on "..." and "View file" on the top right of the document window.

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/9af45540-87b6-47e1-8cdf-384cfb88943e)

I continued to work on this tutorial after several months (!) and finished the small analysis. As described before, I added my modified notebook to the staging state with "git add" and commited with an explicit description. Then, I pushed on the branch I was working on. Here is the result on github:

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/2715774a-fc83-4955-a58a-c3c4f6005ed9)


The second commit corresponds to the commit I just pushed. It contains the modifications I made in my notebook.

# 4 - Merge your branch with the main branch

I consider that my job is done, so in a company context I would ask my coworkers to review my work and leave comments. Then, I would take their comments into consideration to produce the best work possible. Finally, everyone would be very happy with this work and approve this pull request ! 
Since I am alone, I consider that my job is done and that I can merge this work on the main branch. There is a button on github that does it automatically:

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/862df586-9579-4c2f-b7e5-61535879c486)


Note that we can merge only if there are no conflicts with the main branch. This can happen when other people work on files and push them on the main branch with some modifications that you do not have on your branch yet. This can be easily resolved by a "git rebase" (this is a more intermediate git method so I will juste leave a tutorial here https://www.freecodecamp.org/news/how-to-use-git-rebase/ but feel free to ask questions on the Discord server).

After merging, I can delete my old branch since all work is now on the main branch : 

![image](https://github.com/FoMelanie/Github_tutorial/assets/87911606/85ce3ca0-fa5a-491b-a6e6-e205fb43ebff)


And voilà ! Now you know the basics of git and you can use it directly with Anaconda navigator and your Notebook. Feel free to make comments and ask questions on the Discord server ! I hope this helps some people to work with git and github. See you !



