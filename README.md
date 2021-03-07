# fakeapi

A [Mockend](https://mockend.com/) implements to mock my REST or GraphQL API

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
