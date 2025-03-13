# /lesson

#### Lesson

This model represents educational lessons that can be created, edited, viewed, or deleted. This appears in the Learning Hub on the Project, should the config be enabled.

**Permissions**

* **GET:** Retrieve lessons.
* **POST:** Create new lessons.
* **PATCH:** Update specific fields of a lesson.
* **PUT:** Replace an existing lesson.
* **DELETE:** Permanently remove a lesson from the database.
* **SOFT\_DELETE:** Mark a lesson as deleted without permanently removing it from the database.

**Fields**

* **title:** (String, Public, Required, Editable) - The title of the lesson.
* **slug:** (String, Public, Required, Unique, Editable, Indexed) - A unique identifier for the lesson, typically used in URLs.
* **category:** (String, Public, Editable) - The category of the lesson.
* **paid:** (Boolean, Public, Editable) - Indicates if the lesson is paid.
* **tags:** (Array, Public, Editable, Indexed) - Tags associated with the lesson.
* **description:** (String, Public, Editable) - Description of the lesson.
* **summary:** (String, Public, Editable) - A brief summary of the lesson.
* **photo:** (String, Public, Editable) - A photo associated with the lesson.
* **previewVideo:** (String, Public, Editable) - URL of the preview video for the lesson.
* **fullVideo:** (String, Public, Editable) - URL of the full video for the lesson.
* **visibility:** (Enum, Public, Editable, Default: "public", OwnerVisible) - Visibility status of the lesson. Possible values: "public", "custom", "private", "secret".
* **channel:** (String, Public, Editable) - The channel to which the lesson belongs.
* **visibleBy:** (Array, Public, Editable, Default: \[]) - List of users who can see the lesson.
* **reportedBy:** (Array, Default: \[]) - List of users who reported the lesson.
* **createdBy:** (String, Public, Default: null) - User who created the lesson.
* **updated:** (Date, Public) - Last update timestamp.
* **created:** (Date, Public) - Creation timestamp.
* **deleted:** (Date) - Deletion timestamp.
* **attributes:** (Array, Public, Default: \[]) - Additional attributes of the lesson.
* **managedBy:** (Array, Public, Default: \[]) - List of users managing the lesson.

**Sample API Request**

**Endpoint:** `POST /api/lessons`

**Request Body:**

```json
jsonCopy code{
  "title": "Introduction to Permaculture",
  "slug": "introduction-to-permaculture",
  "category": "Sustainable Agriculture",
  "paid": true,
  "tags": ["permaculture", "sustainable", "agriculture"],
  "description": "A comprehensive introduction to permaculture principles and practices.",
  "summary": "Learn the basics of permaculture in this introductory lesson.",
  "photo": "<photo-id>",
  "previewVideo": "http://example.com/videos/intro-to-permaculture-preview.mp4",
  "fullVideo": "http://example.com/videos/intro-to-permaculture-full.mp4",
  "visibility": "public",
  "channel": "education",
  "visibleBy": [],
  "reportedBy": [],
  "createdBy": "instructor123",
  "attributes": [],
  "managedBy": []
}
```

**Response:**

```json
jsonCopy code{
  "id": "lesson123",
  "title": "Introduction to Permaculture",
  "slug": "introduction-to-permaculture",
  "category": "Sustainable Agriculture",
  "paid": true,
  "tags": ["permaculture", "sustainable", "agriculture"],
  "description": "A comprehensive introduction to permaculture principles and practices.",
  "summary": "Learn the basics of permaculture in this introductory lesson.",
  "photo": "<photo-id>",
  "previewVideo": "http://example.com/videos/intro-to-permaculture-preview.mp4",
  "fullVideo": "http://example.com/videos/intro-to-permaculture-full.mp4",
  "visibility": "public",
  "channel": "education",
  "visibleBy": [],
  "reportedBy": [],
  "createdBy": "instructor123",
  "updated": "2024-06-09T12:34:56Z",
  "created": "2024-06-09T12:34:56Z",
  "deleted": null,
  "attributes": [],
  "managedBy": []
}
```
