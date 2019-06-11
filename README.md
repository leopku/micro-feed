# Micro Feed

Micro-Feed an extremely small size feed sync service with GraphQL support(also a graphql playground). https://github.com/leopku/micro-feed

## Screenshot

![screenshot for micro-feed](https://raw.githubusercontent.com/leopku/micro-feed/master/968B077F-D710-4632-9AD6-A9FD4A7D4D29.jpg)

## Features

### Micro Size

Extremely small binary size and docker image size.

Docker image size is <10MB.

### Supported feed types

* RSS 0.90
* Netscape RSS 0.91
* Userland RSS 0.91
* RSS 0.92
* RSS 0.93
* RSS 0.94
* RSS 1.0
* RSS 2.0
* Atom 0.3
* Atom 1.0

## Docker

### Docker image location

[https://hub.docker.com/r/leopku/micro-feed-community](https://hub.docker.com/r/leopku/micro-feed-community)

### Default

* app root: `/app`
* app config: `/app/micro-feed.toml`
* database: `/app/micro-feed.db`. This can be changed by modifing `/app/micro-feed.toml`

## GraphQL

### Playground

* `http://localhost:9300`

### Play with GraphQL 

#### Add a feed

```
mutation {
  createFeed(title: "my new feed", description: "feed detail", subscription: "https://path/of/my/feed/rss.xml")
}
```

After adding feed and waiting for a while (default 15min), entries would be synced from feed.

#### List Entries

```
query {
  entries {
    id
    title
    link
  }
}
```

#### Get detail of an entry

```
query {
  entry(id: 123) {
    id
    title
    link
  }
}
```

#### Mark an entry as read/unread

```
mutation {
  markEntry(id: 123, mark: 1)
}
```

* `1` as read
* `2` as unread

## Issue reporting & Suggestion

### Telegram group

https://t.me/joinchat/BTEzgBdAx6eQKVZj7mFPbA

### Github Issue

https://github.com/leopku/micro-feed/issues
