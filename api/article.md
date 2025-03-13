# /article

Articles appear in the Blog, and can be created, edited, viewed, or deleted. Articles may contain various types of content such as text, images, and metadata.

**Permissions**

* **GET:** Retrieve articles.
* **POST:** Create new articles.
* **PATCH:** Update specific fields of an article.
* **PUT:** Replace an existing article.
* **SOFT\_DELETE:** Mark an article as deleted without permanently removing it from the database.

**Fields**

* **title:** (String, Public, Required, Editable) - The title of the article.
* **slug:** (String, Public, Required, Unique, Editable, Indexed) - A unique identifier for the article, typically used in URLs.
* **category:** (String, Public, Editable) - The category of the article.
* **tags:** (Array, Public, Editable, Indexed) - Tags associated with the article.
* **html:** (String, Public, Editable) - The HTML content of the article.
* **editorState:** (String, Public, Editable) - The state of the editor when the article was created or updated.
* **summary:** (String, Public, Editable) - A brief summary of the article.
* **photo:** (String, Public, Editable) - A photo associated with the article.
* **photoUrl:** (String, Public, Editable) - URL of the photo associated with the article.
* **visibility:** (Enum, Public, Editable, Default: "public", OwnerVisible) - Visibility status of the article. Possible values: "public", "custom", "private", "secret".
* **channel:** (String, Public, Editable) - The channel to which the article belongs.
* **visibleBy:** (Array, Public, Editable, Default: \[]) - List of users who can see the article.
* **reportedBy:** (Array, Default: \[]) - List of users who reported the article.
* **createdBy:** (String, Public, Default: null) - User who created the article.
* **updated:** (Date, Public) - Last update timestamp.
* **created:** (Date, Public) - Creation timestamp.
* **deleted:** (Date) - Deletion timestamp.
* **attributes:** (Array, Public, Default: \[]) - Additional attributes of the article.
* **managedBy:** (Array, Public, Default: \[]) - List of users managing the article.





#### Sample API Request

**Create a New Article**

**Endpoint:** `POST /api/articles`

Request Body:

```jsx
{
  "title": "Introduction to Regenerative Agriculture",
  "slug": "introduction-to-regenerative-agriculture",
  "category": "Sustainable Farming",
  "tags": ["regenerative", "agriculture", "farming"],
  "html": "<p>This is an introduction to regenerative agriculture...</p>",
  "editorState": "<editor-state>",
  "summary": "An overview of the principles and practices of regenerative agriculture.",
  "photo": "<photo-id>",
  "photoUrl": "http://example.com/images/regenerative-agriculture.jpg",
  "visibility": "public",
  "channel": "agriculture-news",
  "visibleBy": [],
  "reportedBy": [],
  "createdBy": "user123",
  "attributes": [],
  "managedBy": []
}

```



Response:

```
{
  "id": "article123",
  "title": "Introduction to Regenerative Agriculture",
  "slug": "introduction-to-regenerative-agriculture",
  "category": "Sustainable Farming",
  "tags": ["regenerative", "agriculture", "farming"],
  "html": "<p>This is an introduction to regenerative agriculture...</p>",
  "editorState": "<editor-state>",
  "summary": "An overview of the principles and practices of regenerative agriculture.",
  "photo": "<photo-id>",
  "photoUrl": "http://example.com/images/regenerative-agriculture.jpg",
  "visibility": "public",
  "channel": "agriculture-news",
  "visibleBy": [],
  "reportedBy": [],
  "createdBy": "user123",
  "updated": "2024-06-09T12:34:56Z",
  "created": "2024-06-09T12:34:56Z",
  "deleted": null,
  "attributes": [],
  "managedBy": []
}

```
