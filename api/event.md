# /event

This model is used to manage events, including their details, categories, and participation options.

**Permissions**

* **GET:** Retrieve events.
* **POST:** Create new events.
* **PATCH:** Update specific fields of an event.
* **PUT:** Replace an existing event.
* **DELETE:** Permanently remove an event from the database.
* **SOFT\_DELETE:** Mark an event as deleted without permanently removing it from the database.

**Fields**

* **name:** (String, Public, Editable) - Name of the event.
* **host:** (String, Public, Editable) - Host of the event.
* **stripePub:** (String, Public, Editable) - Public Stripe key for payment processing.
* **stripeKey:** (String, Private, Editable) - Private Stripe key for payment processing.
* **recording:** (String, Public, Editable) - URL of the event recording.
* **rep:** (Array, Public, Editable) - Representative information.
* **visual:** (String, Public, Editable) - Visual representation of the event.
* **password:** (String, Public, Editable) - Password for accessing the event.
* **category:** (String, Public, Editable) - Category of the event.
* **photo:** (String, Public, Editable) - Photo associated with the event.
* **slug:** (String, Public, Required, Unique, Editable, Indexed) - A unique identifier for the event, typically used in URLs.
* **description:** (String, Public, Editable) - Description of the event.
* **participationGuideUrl:** (String, Public, Editable) - URL of the participation guide.
* **ticket:** (String, Public, Editable) - Ticket information for the event.
* **virtual:** (Boolean, Public, Editable) - Indicates if the event is virtual.
* **paid:** (Boolean, Public, Editable) - Indicates if the event is paid.
* **featured:** (Boolean, Public, Editable) - Indicates if the event is featured.
* **blocksBookingCalendar:** (Boolean, Public, Editable, Default: false) - Indicates if the event blocks booking calendar.
* **location:** (String, Public, Editable) - Location of the event.
* **address:** (String, Public, Editable) - Address of the event.
* **attendees:** (Array, Public, Editable, Default: \[]) - List of attendees.
* **speakers:** (Array, Public, Editable, Default: \[]) - List of speakers.
* **ticketOptions:** (Array, Public, Editable) - Various ticket options available for the event.
* **fields:** (Array, Public, Editable) - Custom fields for the event.
* **partners:** (Array, Public, Editable) - Partners associated with the event.
* **ticketOptionsDisclaimer:** (String, Public, Editable) - Disclaimer for the ticket options.
* **price:** (Number, Public, Editable) - Price of the event.
* **transportOptions:** (Array, Public, Editable) - Transport options available for the event.
* **volunteerDiscount:** (Number, Public, Editable) - Discount available for volunteers.
* **discounts:** (Array, Public, Editable) - Discounts available for the event.
* **capacity:** (Number, Public, Editable, Default: 0) - Capacity of the event.
* **start:** (Date, Public, Editable) - Start date and time of the event.
* **end:** (Date, Public, Editable) - End date and time of the event.
* **visibility:** (Enum, Public, Editable, Default: "public", OwnerVisible) - Visibility status of the event. Possible values: "public", "custom", "private", "secret".
* **channel:** (String, Public, Editable) - The channel to which the event belongs.
* **visibleBy:** (Array, Public, Editable, Default: \[]) - List of users who can see the event.
* **reportedBy:** (Array, Default: \[]) - List of users who reported the event.
* **createdBy:** (String, Public, Default: null) - User who created the event.
* **updated:** (Date, Public) - Last update timestamp.
* **created:** (Date, Public) - Creation timestamp.
* **deleted:** (Date) - Deletion timestamp.
* **attributes:** (Array, Public, Default: \[]) - Additional attributes of the event.
* **managedBy:** (Array, Public, Default: \[]) - List of users managing the event.

**Sample API Request**

**Endpoint:** `POST /api/events`

**Request Body:**

```json
jsonCopy code{
  "name": "Sustainable Living Workshop",
  "host": "Green Earth Initiative",
  "stripePub": "pk_live_1234567890",
  "stripeKey": "sk_test_1234567890",
  "recording": "http://example.com/recordings/sustainable-living.mp4",
  "rep": [],
  "visual": "http://example.com/images/sustainable-living.jpg",
  "password": "workshop2024",
  "category": "Workshops",
  "photo": "<photo-id>",
  "slug": "sustainable-living-workshop",
  "description": "Join us for a workshop on sustainable living practices.",
  "participationGuideUrl": "http://example.com/guides/participation.pdf",
  "ticket": "ticket123",
  "virtual": true,
  "paid": true,
  "featured": true,
  "blocksBookingCalendar": false,
  "location": "Online",
  "address": "",
  "attendees": [],
  "speakers": [],
  "ticketOptions": [],
  "fields": [],
  "partners": [],
  "ticketOptionsDisclaimer": "All sales are final.",
  "price": 50.00,
  "transportOptions": [],
  "volunteerDiscount": 10.00,
  "discounts": [],
  "capacity": 100,
  "start": "2024-08-01T10:00:00Z",
  "end": "2024-08-01T12:00:00Z",
  "visibility": "public",
  "channel": "events",
  "visibleBy": [],
  "reportedBy": [],
  "createdBy": "organizer123",
  "attributes": [],
  "managedBy": []
}
```

**Response:**

```json
jsonCopy code{
  "id": "event123",
  "name": "Sustainable Living Workshop",
  "host": "Green Earth Initiative",
  "stripePub": "pk_live_1234567890",
  "stripeKey": "sk_test_1234567890",
  "recording": "http://example.com/recordings/sustainable-living.mp4",
  "rep": [],
  "visual": "http://example.com/images/sustainable-living.jpg",
  "password": "workshop2024",
  "category": "Workshops",
  "photo": "<photo-id>",
  "slug": "sustainable-living-workshop",
  "description": "Join us for a workshop on sustainable living practices.",
  "participationGuideUrl": "http://example.com/guides/participation.pdf",
  "ticket": "ticket123",
  "virtual": true,
  "paid": true,
  "featured": true,
  "blocksBookingCalendar": false,
  "location": "Online",
  "address": "",
  "attendees": [],
  "speakers": [],
  "ticketOptions": [],
  "fields": [],
  "partners": [],
  "ticketOptionsDisclaimer": "All sales are final.",
  "price": 50.00,
  "transportOptions": [],
  "volunteerDiscount": 10.00,
  "discounts": [],
  "capacity": 100,
  "start": "2024-08-01T10:00:00Z",
  "end": "2024-08-01T12:00:00Z",
  "visibility": "public",
  "channel": "events",
  "visibleBy": [],
  "reportedBy": [],
  "createdBy": "organizer123",
  "updated": "2024-06-09T12:34:56Z",
  "created": "2024-06-09T12:34:56Z",
  "deleted": null,
  "attributes": [],
  "managedBy": []
}
```
