# Front-End Coding Challenge

## Requirements

1. Consumes and displays a list of posts from the API. Content Should include

- Title
- Content
- Categories
- Author (Avatar, Name)
- Date
- Comments (optional)

2. Has a form to create a post.

- Includes a "Create Post" button to toggle the view of the form
- Upon submit, form should send a `POST` request to the server and update the view with the new post data on success.
- Form can simply display above list of posts.

3. Has a form to filter the list of posts. Can filter by:

- Keyword (text field)
- Categories (select field)
- Note: Filtering does not need to post to the server. This can just be implemented on the front-end

4. Includes basic styling for post list and forms

## Guidelines

- The API is a mock server that serves data from a static json file. Therefore data from the API is not persisted across subsequent requests.
- The project is set up to use React with plain JavaScript.
- You may import any other libraries you may find helpful to complete the project.
- There is no need to use any specialized tooling like Typescript or other static type checkers, but you may do so if you like.
- You may make any modifications to the files and/or directories as you see fit to match your preferences.
- You may write styles plain css in the default `styles.css` or with whatever CSS preprocesser or JS-in-CSS solution you are comfortable with (this project supports CSS and SCSS out-of-the-box).

## API

### Base

https://my-json-server.typicode.com/wlion/mock-json-server/

### Endpoints:

| Resource   | Endpoint      | Methods | body   | response.data |
| ---------- | ------------- | ------- | ------ | ------------- |
| Posts      | `/posts`      | GET     | N/A    | Array         |
| Posts      | `/posts`      | POST    | Object | Object        |
| Categories | `/categories` | GET     | N/A    | Array         |
| Comments   | `/comments`   | GET     | N/A    | Array         |
| Authors    | `/authors`    | GET     | N/A    | Array         |

#### Example request using `axios`:

```javascript
axios
  .post('https://my-json-server.typicode.com/wlion/mock-json-server/posts', {
    title: 'New Post',
    content: '<p>This is the post content.</p>',
    image: 'http://via.placeholder.com/800x500',
    date: 'Oct 08 2019',
    categories: [1, 2],
    authorId: 3
  })
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.log(error);
  });
```
