# FriendFinder

`Deployed on Heroku @ ` https://arcane-bastion-12586.herokuapp.com/

# Overview
This is a compatibility-based "FriendFinder" application -- basically a dating app. This full-stack site takes in results from users' surveys, then compare their answers with those from other users. The app then displays the name and picture of the user with the best overall match.

This application uses Express to handle routing and is deployed to Heroku so other users can fill it out.

The survey has 10 questions each answer on a scale of 1 to 5 based on how much the user agrees or disagrees with a question.

The user's most compatible friend is calculated using the following as a guide:

  * Convert each user's results into a simple array of numbers (ex: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`).
  * With that done, compare the difference between current user's scores against those from other users, question by question. Add up the differences to calculate the `totalDifference`.
      * Example:
        * User 1: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`
        * User 2: `[3, 2, 6, 4, 5, 1, 2, 5, 4, 1]`
        * Total Difference: **2 + 1 + 2 =** **_5_**
    * Use the absolute value of the differences. Put another way: no negative solutions! Calculate both `5-3` and `3-5` as `2`, and so on.
    * The closest match will be the user with the least amount of difference.