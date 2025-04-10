# API Documentation for Closer Platform

Welcome to the Closer Platform API. This public documentation provides an overview of the available endpoints that let you create, read, update, and delete (CRUD) various types of data within the platform. The API is RESTful and uses JSON for requests and responses.

> **Authentication:**  
> To use our API, include your API key in the HTTP header as follows:  
> `Authorization: Bearer YOUR_API_KEY`

---

## Table of Contents

1. [Articles](#articles)
2. [Applications](#applications)
3. [Bookings](#bookings)
4. [Configurations](#configurations)
5. [Lessons](#lessons)
6. [Channels](#channels)
7. [Events](#events)
8. [Tickets](#tickets)
9. [Listings](#listings)
10. [Messages](#messages)
11. [Metrics](#metrics)
12. [Partners](#partners)
13. [Posts](#posts)
14. [Products](#products)
15. [Photos](#photos)
16. [Resources](#resources)
17. [Sessions](#sessions)
18. [Stays](#stays)
19. [Users](#users)
20. [Volunteers](#volunteers)
21. [Food](#food)
22. [Charges](#charges)
23. [Projects](#projects)
24. [Pages](#pages)

---

## 1. Articles

**Purpose:** Manage content articles like blog posts or announcements.  
**Supported Methods:** GET, POST, PATCH, PUT, SOFT_DELETE, DELETE

**Key Fields:**
- `title` (required, editable)
- `slug` (required, unique, editable)
- `category`, `tags`, `html`, `summary`, `photo`, `photoUrl`
- `visibility` (options: public, custom, private, secret)

---

## 2. Applications

**Purpose:** Handle user applications or join requests.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE

**Key Fields:**
- `type` (e.g., "user")
- `status` (e.g., "open")
- `name`, `email`, `phone`
- `viewChannels`
- `visibility`

---

## 3. Bookings

**Purpose:** Manage booking records for stays, events, or volunteer appointments.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `status`, `checkin`, `checkout`, `listing`
- `description`, `message`
- `foodOption` (options: basic, chef, no_food)
- `eventId`
- Additional pricing and booking details

---

## 4. Configurations

**Purpose:** Retrieve and update system configuration settings.  
**Supported Methods:** GET, PATCH, POST

**Key Fields:**
- `slug` (required, unique)
- `value` (object containing configuration data)
- `visibility`

---

## 5. Lessons

**Purpose:** Manage courses and lesson content in the Learning Hub.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `title`, `slug`
- `category`, `tags`
- `description`, `summary`
- `photo`, `previewVideo`, `fullVideo`
- `visibility`

---

## 6. Channels

**Purpose:** Organize and manage communication channels.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE

**Key Fields:**
- `name`, `slug`
- `description`
- `visibility`

---

## 7. Events

**Purpose:** Create and manage events such as community gatherings or workshops.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `name`, `host`, `slug`
- `description`, `participationGuideUrl`
- `ticket`, `virtual`
- `capacity`, `start`, `end`
- `visibility`  
- Option to block the booking calendar during the event

---

## 8. Tickets

**Purpose:** Retrieve ticket information for events.  
**Supported Methods:** GET

**Key Fields:**
- `name`, `quantity`
- `email`, `status`
- Associated `event` and `booking`
- `price`
- `visibility`

---

## 9. Listings

**Purpose:** Manage accommodation or resource listings on the platform.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `name`, `category`, `photo`, `photos`
- `slug`, `description`
- `priceDuration`, `fiatPrice`, `tokenPrice`
- `quantity`, `availableFor`
- `visibility`

---

## 10. Messages

**Purpose:** Handle messages for communications, chat support, and notifications.  
**Supported Methods:** GET, POST, PATCH, PUT, SOFT_DELETE

**Key Fields:**
- `room`, `content`, `meta`
- `visibility`, `channel`

---

## 11. Metrics

**Purpose:** Record and retrieve performance metrics and usage data.  
**Supported Methods:** GET, POST

**Key Fields:**
- `point`, `event`
- `value`, `category`
- `visibility`

---

## 12. Partners

**Purpose:** Manage partner profiles and collaboration details.  
**Supported Methods:** GET, POST, PATCH, PUT, SOFT_DELETE

**Key Fields:**
- `name`, `slug`
- `description`, `story`
- `url`, `video`
- `visibility`

---

## 13. Posts

**Purpose:** Handle social posts and discussion threads.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE

**Key Fields:**
- `category`, `content`, `slug`
- `replyCount`, `parentType`, `parentId`
- `photo`, `tags`, `meta`
- `visibility`

---

## 14. Products

**Purpose:** Manage products for sale, including digital and physical goods.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `name`, `category`, `photos`
- `slug`, `description`, `price`
- `digital_product_url`, `quantity`, `discounts`
- `visibility`

---

## 15. Photos

**Purpose:** Handle photo uploads and management.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE

**Key Fields:**
- `slug`, `ipfs`, `urls`, `extension`
- `users`, `likedBy`
- `location`
- `visibility`

---

## 16. Resources

**Purpose:** Manage resource materials such as guides or documentation links.  
**Supported Methods:** GET, POST, PATCH, PUT, SOFT_DELETE

**Key Fields:**
- `category`, `title`, `slug`
- `content`, `ctaText`, `url`
- `visibility`

---

## 17. Sessions

**Purpose:** Manage live sessions or meetings, including scheduling and attendance tracking.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `name`, `description`, `speakers`, `category`
- `photo`, `event`, `slug`
- `attendees`, `start`, `end`
- `visibility`

---

## 18. Stays

**Purpose:** Retrieve records that link users to their accommodation bookings.  
**Supported Methods:** GET

**Key Fields:**
- `userId`, `bookingId`, `amount`
- `source`, `expiry`
- `visibility`

---

## 19. Users

**Purpose:** Manage user profiles and account details.  
**Supported Methods:** GET, POST, PATCH, DELETE

**Key Fields:**
- `screenname`, `slug`
- `email`, `walletAddress`, `photo`
- `subscription`, `citizenship`, `roles`
- `preferences`, `settings`, `links`, `stats`
- `vouched`, `visibility`

---

## 20. Volunteers

**Purpose:** Manage volunteer applications and profiles.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `name`, `category`, `residency`, `commitment`
- `photo`, `slug`, `description`
- `start`, `end`
- `visibility`

---

## 21. Food

**Purpose:** Manage food options available for bookings or events.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `name`, `photos`, `slug`, `description`
- `price`, `isDefault`
- `visibility`

---

## 22. Charges

**Purpose:** Manage payment transactions and charge records (linked to bookings or products).  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `id`, `type`, `method`
- `bookingId`, `productId`
- `status`, `date`, `amount`
- `meta`, `referredBy`, `affiliateRevenue`
- `visibility`

---

## 23. Projects

**Purpose:** Manage community projects, including timelines, skills, and budgets.  
**Supported Methods:** GET, POST, PATCH, PUT, DELETE, SOFT_DELETE

**Key Fields:**
- `name`, `category`, `residency`, `commitment`
- `photo`, `slug`, `description`
- `start`, `end`, `skills`, `reward`
- `documentUrl`, `estimate`, `budget`
- `visibility`

---

## 24. Pages

**Purpose:** Manage dynamic web pages (e.g., homepage, FAQs, about pages).  
**Supported Methods:** GET, POST, PATCH, PUT, SOFT_DELETE, DELETE

**Key Fields:**
- `isHomePage` (marks a page as the main homepage)
- `photos`, `faqsSheetId`, `resources`
- `showUpcomingEvents`, `sections`
- `visibility`
