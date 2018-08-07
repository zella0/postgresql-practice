## Join Assignments
CREATE `users` database via postico and then run the command below from terminal.
- psql users -f seed1.sql


### Challenge 1:
Select all posts and display the user that created the post.
- SELECT * FROM posts
  JOIN users
  ON posts.user_id = users.id;

### Challenge 2:
Select all posts made by the user with the id of 3.
- SELECT * FROM posts
  WHERE posts.user_id = 3;

### Challenge 3:
Display all users and the posts they made. Display a user even if they haven't made a post.
- SELECT * FROM users
  FULL JOIN posts
  ON posts.user_id = users.id;

### Challenge 4:
Display all users and their posts ordered by age (from greatest age to lowest).
- SELECT * FROM users
  FULL JOIN posts
  ON posts.user_id = users.id
  ORDER BY age DESC;

### Challenge 5 (stretch):
Display each users first name along with the number of posts they have made.
- SELECT users.first_name, COUNT(posts.user_id)
	FROM users
	FULL JOIN posts ON users.id = posts.user_id
	GROUP BY users.first_name
	ORDER BY count DESC;


## Part 2:
For part 2 run the command below in terminal:
- psql users -f seed2.sql

### Challenge 6:
Display all comments and the contents of the post they were made on.
- SELECT comments AS user_comment, posts.content
  FROM comments
  JOIN posts ON comments.user_id = posts.user_id

### Challenge 7:
Display all comments with the contents of the post and the user that made the comment.
- SELECT comments.content AS user_comment, posts.content, posts.user_id
  FROM comments
  JOIN posts ON comments.user_id = posts.user_id

### Challenge 8:
Display all comments where the user who wrote the comment has an age > 30.
- SELECT comments.content AS user_comment, age
  FROM comments
  JOIN users ON comments.user_id = users.id WHERE users.age > 30;


### Challenge 9:
Display all the posts along with what user made the post, also display any comments along with the users first name that made the comment.
- SELECT posts.content AS posts, users.first_name, comments.content AS comment, comment_user.first_name AS commenter_name
  FROM posts
  LEFT JOIN users ON posts.user_id = users.id
  LEFT JOIN comments ON comments.post_id = posts.id
  LEFT JOIN users AS comment_user ON comment_user.id = comments.user_id;

### Challenge 10:
Display all the posts with what user made the post, also display the total count of comments each post has.

- SELECT posts.content AS posts, users.first_name AS Post_Author, COUNT(comments.post_id)
  FROM posts
  LEFT JOIN users ON users.id = posts.user_id
  LEFT JOIN comments ON comments.post_id = posts.id
  GROUP BY posts.content, users.first_name, comments.post_id
  ORDER BY count DESC;
