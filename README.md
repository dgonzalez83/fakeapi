# fakeapi

A [Mockend](https://mockend.com/) implements to mock my REST or GraphQL API. You can check official documentation [here](https://docs.mockend.com/).
 
## Installation

Install Mockend GitHub app on your repo. For the rest of the docs, we'll consider it's org/repo.

Create a `.mockend.json` file to describe your API.

## Configuration

Supported types are: `string`, `int`, `boolean` and `date`.

You can also describe `has many` and `belongs` to relations.

For example:

```json
{
  "Post": {
    "title": "string",
    "views": "int",
    "published": "boolean",
    "createdAt": "date",
    "comments": "Comment[]"
  },
  "Comment": {
    "body": "string",
    "post": "Post"
  }
}
```

## Routes

For REST, based on the previous config, the following routes will be created:

```bash
GET https://mockend.com/org/repo/posts
GET https://mockend.com/org/repo/posts/<id>
GET https://mockend.com/org/repo/comments
GET https://mockend.com/org/repo/comments/<id>
```

Routes can take query parameters, see below.

GraphQL, will be available at:

```bash
https://mockend.com/org/repo/graphql
```

**Mockend supports Git branches**, you can therefore have multiple mock APIs for different features on the same repo.

Simply add `tree/:branch_name` to your URL, for example:

```bash
/org/repo/tree/my-awesome-feature/graphql
```

## Queries

### REST

...

### GraphQL

...
