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

```
GET https://mockend.com/org/repo/posts
GET https://mockend.com/org/repo/posts/<id>
GET https://mockend.com/org/repo/comments
GET https://mockend.com/org/repo/comments/<id>
```

Routes can take query parameters, see below.

GraphQL, will be available at:

```
https://mockend.com/org/repo/graphql
```

**Mockend supports Git branches**, you can therefore have multiple mock APIs for different features on the same repo.

Simply add `tree/:branch_name` to your URL, for example:

```
/org/repo/tree/my-awesome-feature/graphql
```

## Queries

### REST

Query parameters can be used to filter, sort and paginate lists:

- `_eq` `_ne`
        equal, not equal
- `_gt` _`lt`
        greater than, lower than
- `_order`
        sort data (`asc` `desc`)
- `limit` `offset`
        use them to paginate your results

For example:

```
GET /posts?date_order=desc

GET /posts
    ?views_gt=10
    &published_eq=true
    &views_order=desc
    &limit=5
```

### GraphQL

A GraphiQL interface, with specific documentation for your API, can be found directly at:

```
https://mockend.com/org/repo/graphql
```
