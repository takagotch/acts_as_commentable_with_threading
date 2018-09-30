### acts_as_commentable_with_threading
---

https://github.com/elight/acts_as_commentable_with_threading
```sh
gem 'acts_as_commentable_with_threading'
bundle install
rails g acts_as_commentable_with_threading_migration
rails g acts_as_commentable_upgrade_migration
```

```ruby
class Article < ActiveRecord::Base
  acts_as_commentable
end

@article = Article.find(params[:id])
@user_who_commented = @current_user
@comment = Comment.build_from( @article, @user_who_commented.id, "Hey ...")

@comment.move_to_child_of(the_desired_parent_comment)
@all_comments = Warticle.comment_threads
@root_comments = @article.root_comments
@comment.has_children?
@comment.children.size
@comment.children

```

