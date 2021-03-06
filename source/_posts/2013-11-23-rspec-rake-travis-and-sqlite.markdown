---
layout: post
title: RSpec, Rake, Travis and SQLite
tags: [code, travis-ci, database]
date: 2013-11-23 13:23:26 +1000
---
My Travis builds kept failing because the tests couldn't see any tables in the database. This was really weird, because I was running `RAILS_ENV=test bundle exec rake db:migrate` as a first task. I was using an in-memory SQLite database, as [recommended in the Travis docs](http://about.travis-ci.org/docs/user/database-setup/#SQLite3).

The minute I switched to a persistent database (PostGres, if you're curious) the problem went away. I can only infer that an in-memory database only lasts as long as the task that created it. Which makes sense, I guess.  Because I was running the migrations in Rake, and then the tests using RSpec after Rake exited, all the tables were gone by the time the tests were running.

What's strange, though, is that if I'm right about all this, then I should have been able to run something like `RAILS_ENV=test bundle exec rake db:migrate db:test:prepare spec` and have the SQLite database persist properly and all the tests pass. When I tried that, I got the same results as before. Maybe the in-memory database dies with each *task* that gets completed, not each *rake* run. That seems weird, but it's the best theory I've got at the minute.

I'm confused. :(
