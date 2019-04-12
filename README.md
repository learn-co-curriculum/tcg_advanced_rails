# Advanced Rails

## Learning Goals

- Use Rails modules to implement advanced web application features

## Introduction

We've seen that Rails provides tons of common web application functionality out of the box. Surprise! Rails has _way_ more to offer than what Flatiron covers in the curriculum.

This exercise walks through some of the most common and useful advanced features that Rails provides. In order learn these tools in a more meaningful way, you'll be adding each of these to the [Blogger App] that you've already deployed to Heroku.

The basic workflow that you should follow for each of these modules is

- Read the rails docs on the subject
- Design the blogger app feature to use that module
- Implement the feature in your code and deploy it to Heroku

The topics chosen for this lab (and their corresponding Rails modules):

- Auth (several different tools and concepts including sessions, credentials, and secrets)
- Caching (`Rails.cache`, `ActiveSupport::Cache:Store`)
- Storing files (`ActiveStorage`)
- Sending Email (`ActionMailer`)
- Jobs and Queued Work (`ActiveJob`)
- Realtime Messaging (`ActionCable`)

If, after following these guides, you want to dive deeper into more Rails modules, you are encouraged to follow more of the Rails guides and use the blogger application as a testing ground for trying out different features and gems.

## Auth

Start by reading the [Rails Security Guide](https://guides.rubyonrails.org/security.html). It gives an overview of the different security considerations for a web application, and the different Rails built-ins for handling those security concerns.

Next, check out the [JWT Auth walkthrough](https://github.com/learn-co-curriculum/lectures-starter-code/tree/master/react/jwt-auth). The `Walkthrough.md` file guides you to add JWT auth to an application. Follow it to add Auth to your blogger app.

## Caching

Start by reading the [Rails Guide on Caching](https://guides.rubyonrails.org/caching_with_rails.html).

Add caching to the blogger app. Figure out the pages, queries, and computations that are most common and add caching to speed up load times on each of them. You should add some benchmarks or measurements to your application with and without caching so that you can validate that the caching is making a difference.

## Storing Files

Uploading files is a common feature to add to applications. Read the [Rails Guide on ActiveStorage](https://guides.rubyonrails.org/active_storage_overview.html). Add file uploads of some kind to the blogger app - whether that's images, sound files, text files, or something else.

## Sending Email

Most 'real' business applications need to send emails. For instance, any application that has users logging in should send confirmation and password reset emails (in addition to whatever newsletter or spam you'd like to send).

ActionMailer is Rails built-in module for sending email. Read about [ActionMailer Basics](https://guides.rubyonrails.org/action_mailer_basics.html) in the Rails Guides. Then set up mailer on blogger to send some email. 'Subscribe to new posts by author' would be a cool feature, for instance.

## Jobs

Applications have some tasks to do that shouldn't necessarily get done right away - they might take a while, so might block the page response time. ActiveJob is Rails's module for setting jobs to be run later. Read the [Rails Guide on ActiveJob](https://guides.rubyonrails.org/active_job_basics.html) and move your email send into a delayed job. Make sure that you get jobs to run on heroku (the [Heroku guide on DJ](https://devcenter.heroku.com/articles/delayed-job) might be helpful).

If you want an added bonus, set up Resque (or another background job queue). Delayed Job can create extra load on your database, which starts to be a problem when you've got ~100s of transactions per second.

## Realtime Messages

If you want to build features like notifications or chat, you need to be able to send messages from Rails outside of the HTTP request / response cycle. [ActionCable](https://guides.rubyonrails.org/action_cable_overview.html) is Rails's module for setting up websocket connections and sending messages to clients.

Add some realtime features to the blogger app. If you need additional support on understanding websockets and ActionCable, the [Learn Enough Action Cable to be Dangerous tutorial](https://www.learnenough.com/action-cable-tutorial) might be a useful reference.

## Reflection

There are tons common application features that are common enough to have off-the-shelf solutions.

Check out the [Rails 6 Release Notes](https://edgeguides.rubyonrails.org/6_0_release_notes.html) to see what's coming in the next version of Rails. Consider how cool the open source ecosystem is, and how much work so many people do to make software.
