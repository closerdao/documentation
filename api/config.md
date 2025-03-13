# /config

This model is used to manage configuration settings for the application.

**Permissions**

* **GET:** Retrieve configurations.
* **PATCH:** Update specific fields of a configuration.
* **POST:** Add new configuration settings.

**Fields**

* **slug:** (String, Public, Required, Editable, Unique, Indexed, Sparse) - A unique identifier for the configuration.
* **value:** (Object, Public, Editable, Default: {}) - The value of the configuration setting.
* **visibility:** (Enum, Public, Editable, Default: "public", OwnerVisible) - Visibility status of the configuration. Possible values: "public", "custom", "private", "secret".
* **channel:** (String, Public, Editable) - The channel to which the configuration belongs.
* **visibleBy:** (Array, Public, Editable, Default: \[]) - List of users who can see the configuration.
* **reportedBy:** (Array, Default: \[]) - List of users who reported the configuration.
* **createdBy:** (String, Public, Default: null) - User who created the configuration.
* **updated:** (Date, Public) - Last update timestamp.
* **created:** (Date, Public) - Creation timestamp.
* **deleted:** (Date) - Deletion timestamp.
* **attributes:** (Array, Public, Default: \[]) - Additional attributes of the configuration.
* **managedBy:** (Array, Public, Default: \[]) - List of users managing the configuration.

**Sample API Request**

**Endpoint:** `POST /api/configs`

**Request Body:**

```json
jsonCopy code{
  "slug": "site-theme",
  "value": {
    "color": "blue",
    "font": "Arial"
  },
  "visibility": "public",
  "channel": "site-settings",
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
  "id": "config123",
  "slug": "site-theme",
  "value": {
    "color": "blue",
    "font": "Arial"
  },
  "visibility": "public",
  "channel": "site-settings",
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

####
