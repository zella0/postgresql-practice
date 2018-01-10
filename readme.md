## Join Assignments
- CREATE DATABASE users;
- \c users;
- psql users -f seed1.sql


### Challenge 1:
Select all posts and display the user that created the post.

### Challenge 2:
Select all posts made by the user with the id of 3.

### Challenge 3:
Display all users and the posts they made. Display a user even if they haven't made a post.

### Challenge 4:
Display all users and their posts ordered by age (from greatest age to lowest).

### Challenge 5 (stretch):
Display each users first name along with the number of posts they have made.

## Part 2:
For part 2 you'll need to exit out of psql and modify seed2.sql to fit the needs of the challenge.

### Challenge 6:
Inside of seed2.sql create a comments table (similar to posts). The comments table will have a foreign key to both a user and a post.
Create some dummy comments as well.

### Challenge 7:
Display all comments and the contents of the post they were made on.

### Challenge 8:
Display all comments with the contents of the post and the user that made the comment.

### Challenge 8:
Display all comments where the user who wrote the comment has an age > 30.

### Challenge 9:
Display all the posts along with what user made the post, also display any comments along with the users first name that made the comment.

### Challenge 10:
Display all the posts with what user made the post, also display the total count of comments each post has.
