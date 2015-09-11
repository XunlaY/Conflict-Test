# Conflict-Test
Learning by solving a conflict in GIT

This tutorial assumes that you have already set up your IDE and GIT tools.

## Setup
First we need to create a scenario that might happen to you:

1. Clone this repository
2. Initialize Git-Flow
3. You should now be in the `develop` branch.
4. Create a new feature-branch `my-changes`

In this scenario, you've checked out the repository and want to create a new feature while other people might commit something to the `develop` branch.

## Create some changes

1. Ensure you are on the `my-changes` branch.
2. Open the file test.txt
3. The file contains some lorem-ipsum text with 2 markers, telling you how to change the file:
  * `Add a new line of text after this one.`
  * `Change this line of text.`
4. Do those changes.
5. Commit the changes (no need to push).

For example, my test.txt now looks something like this:
```
...
/////////////////
Add a new line of text after this one.
This is a new Line!
///////////////
...
/////////////////
Change this line of text has been changed to something else.
///////////////
...
```
## Create a conflict situation

Now we want to make it look like someone else changed the file on `develop` and pushed it before we could push it.

1. Switch to the `develop` branch.
2. Open the file test.txt, it should be in its original/unmodified state.
3. Apply Changes the same way as described in the section above, but this time choose different words!
4. Commit the changes (no need to push).


Example:
```
...
/////////////////
Add a new line of text after this one.
Here is another line of text!
///////////////
...
/////////////////
This line has been completely changed!
///////////////
...
```

## Finishing the feature

Now the Problem will occur, since you want to get your changes onto the `develop` branch:

1. Switch to the `my-changes` branch.
2. Finish the feature `my-changes` with Git-Flow. This will start merging the feature branch onto `develop`.
3. You will be notified, that conflicts have appeared.
4. In SourceTree you will see a yellow warning icon on the file test.txt (see screenshots below)
5. Rightclick on the file, choose Resolve-Conflicts->Launch External Merge Tool. P4Merge will launch.
6. Merge the files so that both new lines are added and both changed lines are merged to something meaningfull
7. Save the file
8. Commit the changes. (*.orig files can be deleted afterwards)

Always make sure that:

* You don't just replace the code someone else wrote without making sure your code will do the same thing or make it better.
* You always check that the code works BEFORE committing it.

Warning:
![](https://raw.githubusercontent.com/GameDevWeek/Conflict-Test/master/images/warning.png)

P4Merge:
![](https://raw.githubusercontent.com/GameDevWeek/Conflict-Test/master/images/p4merge.png)

Merged conflicts:
![](https://raw.githubusercontent.com/GameDevWeek/Conflict-Test/master/images/merged.png)
