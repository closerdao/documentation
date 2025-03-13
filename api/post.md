# /post

#### Post

This model is used to manage user posts, including content, attachments, and metadata.

Posts can be used in a feed type render.

**Permissions**

* **GET:** Retrieve posts.
* **POST:** Create new posts.
* **PATCH:** Update specific fields of a post.
* **PUT:** Replace an existing post.
* **DELETE:** Permanently remove a post from the database.

**Fields**

* **category:** (String, Public, Editable) - Category of the post.
* **content:** (String, Public, Editable) - Content of the post.
* **slug:** (String, Public, Required, Unique, Editable, Indexed) - A unique identifier for the post, typically used in URLs.
* **replyCount:** (Integer, Public, Editable) - Number of replies to the post.
* **parentType:** (Enum, Public, Editable, Default: "channel") - The type of parent entity. Possible values: "post", "event", "channel", "user".
* **parentId:** (String, Public, Editable) - ID of the parent entity.
* **photo:** (String, Public, Editable) - Photo associated with the post.
* **task:** (String, Public, Editable) - Task information related to the post.
* **attachment:** (String, Public, Editable) - Attachment related to the post.
* **tags:** (Array, Public, Editable, Default: \[]) - Tags associated with the post.
* **meta:** (Object, Public, Editable, Default: {}) - Metadata for the post.
* **visibility:** (Enum, Public, Editable, Default: "public", OwnerVisible) - Visibility status of the post. Possible values: "public", "custom", "private", "secret".
* **channel:** (String, Public, Editable) - The channel to which the post belongs.
* **visibleBy:** (Array, Public, Editable, Default: \[]) - List of users who can see the post.
* **reportedBy:** (Array, Default: \[]) - List of users who reported the post.
* **createdBy:** (String, Public, Default: null) - User who created the post.
* **updated:** (Date, Public) - Last update timestamp.
* **created:** (Date, Public) - Creation timestamp.
* **deleted:** (Date) - Deletion timestamp.
* **attributes:** (Array, Public, Default: \[]) - Additional attributes of the post.
* **managedBy:** (Array, Public, Default: \[]) - List of users managing the post.

**Sample API Request**

**Endpoint:** `POST /api/posts`

**Request Body:**

```json
jsonCopy code{
  "category": "Announcements",
  "content": "We are excited to announce our upcoming event!",
  "slug": "upcoming-event-announcement",
  "replyCount": 0,
  "parentType": "channel",
  "parentId": "channel123",
  "photo": "<photo-id>",
  "task": "spread the word",
  "attachment": "<attachment-id>",
  "tags": ["announcement", "event"],
  "meta": {
    "priority": "high"
  },
  "visibility": "public",
  "channel": "announcements",
  "visibleBy": [],
  "reportedBy": [],
  "createdBy": "admin123",
  "attributes": [],
  "managedBy": []
}
```

**Response:**

```json
jsonCopy code{
  "id": "post123",
  "category": "Announcements",
  "content": "We are excited to announce our upcoming event!",
  "slug": "upcoming-event-announcement",
  "replyCount": 0,
  "parentType": "channel",
  "parentId": "channel123",
  "photo": "<photo-id>",
  "task": "spread the word",
  "attachment": "<attachment-id>",
  "tags": ["announcement", "event"],
  "meta": {
    "priority": "high"
  },
  "visibility": "public",
  "channel": "announcements",
  "visibleBy": [],
  "reportedBy": [],
  "createdBy": "admin123",
  "updated": "2024-06-09T12:34:56Z",
  "created": "2024-06-09T12:34:56Z",
  "deleted": null,
  "attributes": [],
  "managedBy": []
}
```
