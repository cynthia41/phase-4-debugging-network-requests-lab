# Putting it All Together: Client-Server Communication

## Learning Goals

- Understand how to communicate between client and server using fetch, and how
  the server will process the request based on the URL, HTTP verb, and request
  body
- Debug common problems that occur as part of the request-response cycle

## Introduction

Just like the last lesson, we've got code for a React frontend and Rails API
backend set up. This time though, it's up to you to use your debugging skills to
find and fix the errors!

To get the backend set up, run:

```console
$ bundle install
$ rails db:migrate db:seed
$ rails s
```

Then, in a new terminal, run the frontend:

```console
$ npm install --prefix client
$ npm start --prefix client
```

Confirm both applications are up and running by visiting
[`localhost:4000`](http://localhost:4000) and viewing the list of toys in your
React application.

## Deliverables

In this application, we have the following features:

- Display a list of all the toys
- Add a new toy when the toy form is submitted
- Update the number of likes for a toy
- Donate a toy to Goodwill (and delete it from our database)

The code is in place for all these features on our frontend, but there are some
problems with our API! We're able to display all the toys, but the other three
features are broken.

Use your debugging tools to find and fix these issues.

There are no tests for this lesson, so you'll need to do your debugging in the
browser and using the Rails server logs and `byebug`.

**Note**: You shouldn't need to modify any of the React code to get the
application working. You should only need to change the code for the Rails API.

As you work on debugging these issues, use the space in this README file to take
notes about your debugging process. Being a strong debugger is all about
developing a process, and it's helpful to document your steps as part of
developing your own process.

## Your Notes Here

- Add a new toy when the toy form is submitted

  - How I debugged:
  After trying to submit a new toy the server responded with an error which was as a result of a typo in the create method so i changed the name in the toys_controller.rb in the create method from Toys.create to Toy.create after that it became a success.

- Update the number of likes for a toy

  - How I debugged:
  after trying to submit a like for a toy the server returned an error uncaught syntax error: unexpected end of json meaning they are unable to update likes on the frontend so i rendered json on the update method in the toys_controller.rb render json: toys, status: :accepted

- Donate a toy to Goodwill (and delete it from our database)

  - How I debugged:
  After clicking the donate to Goodwill button the server returned an error Delete 404 (Not Found) meaning there was no route to support the destroy method in the controllers so i added a destroy route in the routes.rb file 
