# Front-End Coding Challenge

## Setup

1. Create an account on [CodeSandbox](https://codesandbox.io/).

2. Fork the following project and save it in your account: [White Lion - Candidate Take Home Project](https://codesandbox.io/s/white-lion-candidate-take-home-project-3e1ri).

3. Change the name of your project to "White Lion - Candidate Take Home Project - YOUR FULL NAME".

4. Ensure that you are logged into your account while working on the coding challenge to ensure that your work is auto-saved. If you want to manually save your work, your may press <kbd>CMD</kbd> + <kbd>S</kbd> at any time.

5. To ensure no work is lost, we advise you to keep a local backup of your work. You may do this by clicking "Export to Zip" under the "File" menu within CodeSandbox.

## Requirements

1. Consumes and displays a list of posts from the API. Content should include:

   - Title
   - Content
   - Categories
   - Author (Avatar, Name)
   - Date

2. Has a form to create a new post.

   - Fields should include:
     - Title (text)
     - Content (textarea)
     - Categories (multi-select)
     - Author (select)
     - Date (hidden/disabled - auto-populate based on current date)
   - Upon submit, form should send a `POST` request to the server. On success, form should hide and the new post should be added to the list of posts.
   - Includes "Add New" and "Cancel" buttons to toggle the view of the form. When visible, the form can simply display above list of posts.

3. Has a form to filter the list of posts. Can filter by:

   - Keyword (text)
   - Categories (select)
   - Note: Filtering does not need to post to the server. This can just be implemented on the front-end

4. Includes basic styling for post list and forms.

## Bonus

1. Include simple form validation.
2. Display a thread of comments (no nesting) for the posts.
3. Include comments form to add a comment to a post.

## Guidelines

- The API is a mock server that serves data from a static json file. Therefore data from the API is not persisted across subsequent requests.
- The project is set up to use React with plain JavaScript.
- You may import any other libraries you may find helpful to complete the project.
- You may make any modifications to the files and/or directories as you see fit to match your preferences.
- You may write styles in plain CSS in the default `styles.css` or with whatever CSS preprocesser or JS-in-CSS solution you are comfortable with.
- No need to include tests or to use any specialized tooling like Typescript or other static type checkers, but you may do so if you like.

## API

### Base URL

[https://my-json-server.typicode.com/wlion/coding-challenge-api/](https://my-json-server.typicode.com/wlion/coding-challenge-api/)

### Endpoints:

| Resource   | Endpoint      | Method | body   | response.data |
| ---------- | ------------- | ------ | ------ | ------------- |
| Posts      | `/posts`      | `GET`  | N/A    | Array         |
| Posts      | `/posts`      | `POST` | Object | Object        |
| Categories | `/categories` | `GET`  | N/A    | Array         |
| Comments   | `/comments`   | `GET`  | N/A    | Array         |
| Comments   | `/comments`   | `POST` | Object | Object        |
| Authors    | `/authors`    | `GET`  | N/A    | Array         |

_Example request using `axios`:_

```javascript
axios
  .post(
    'https://my-json-server.typicode.com/wlion/coding-challenge-api/posts',
    {
      title: 'New Post',
      content: '<p>This is the post content.</p>',
      image: 'http://via.placeholder.com/800x500',
      date: 'Oct 08 2019',
      categories: [1, 2],
      authorId: 3
    }
  )
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.log(error);
  });
```
