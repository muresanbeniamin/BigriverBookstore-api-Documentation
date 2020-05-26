---
title: API Reference

includes:
  - errors

search: true
---

# Introduction

Welcome to the BigriverBookstore API. You can use our API to access some of our API endpoints, which can get precious information on various books in our database.

# Books

## Get All Books

```json
{
  "data": [
    {
      "id": "12",
      "type": "book",
      "attributes": {
        "title": "Unlocking Android",
        "author": "W. Frank Ableson",
        "isbn": "1933988673",
        "release_year": 2009,
        "image_url": "https://s3.amazonaws.com/AKIAJC5RLADLUMVRPFDQ.book-thumb-images/ableson.jpg"
      }
    },
    {
      "id": "13",
      "type": "book",
      "attributes": {
        "title": "Android in Action, Second Edition",
        "author": "W. Frank Ableson",
        "isbn": "1935182722",
        "release_year": 2011,
        "image_url": "https://s3.amazonaws.com/AKIAJC5RLADLUMVRPFDQ.book-thumb-images/ableson2.jpg"
      }
    },
  ...
    {
      "id": "21",
      "type": "book",
      "attributes": {
        "title": "OSGi in Depth",
        "author": "Alexandre de Castro Alves",
        "isbn": "193518217X",
        "release_year": 2011,
        "image_url": "https://s3.amazonaws.com/AKIAJC5RLADLUMVRPFDQ.book-thumb-images/alves.jpg"
      }
    }
  ]
```

This endpoint retrieves all books paginated.

### HTTP Request

`GET /v1/books`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | If set any other positive non-negative integer, there will be only retrieved the books from the given page .
by_title | "" | If set to any string, it retrieves the books that match the given value.
by_genre_ids | "" | If set to any string of numbers separated by comma, e.g (?by_genre_ids=1,3,12) the books belonging to given genre ids are retrieved


## Get a Specific Book

```json
{
  "data": {
    "id": "35",
    "type": "book",
    "attributes": {
      "title": "Unlocking Android",
      "author": "W. Frank Ableson",
      "isbn": "1933988673",
      "release_year": 2009,
      "image_url": "https://s3.amazonaws.com/AKIAJC5RLADLUMVRPFDQ.book-thumb-images/ableson.jpg",
      "description": "Android is an open source mobile phone platform based on the Linux operating system and developed by the Open Handset Alliance, a consortium of over 30 hardware, software and telecom companies that focus on open standards for mobile devices."
    }
  }
}
```

This endpoint retrieves a specific book.

### HTTP Request

`GET http://example.com/kittens/:id`

### URL Parameters

Parameter | Description
--------- | -----------
id | The ID of the book to retrieve
