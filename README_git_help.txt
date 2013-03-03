git status 								:: same as svn stat -u (repository status check)
git add bank.cpp						:: (we are ok with changes to bank.cpp)
git commit -m "explanation of commit"
git push origin master					:: scn up i think (send update to git)

git log 								:: history
git reflog								:: history just messages
git show								:: shows last commit and what you change
		-h								:: help (show options git show -h)
gitk									:: gui commit history
git checkout readme						:: quick revert before git add ...
git commit -am "description"			:: -a (is add)

to revert after update
git reflog find hex no. associated with the change you want
git reset --hard [<commit>] 0a52675

git diff <filename>
