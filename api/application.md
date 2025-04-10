# Application Endpoint Documentation

## Description
The Application endpoint handles user applications and join requests for the community.

## Fields
- **type**: string (default: "user", editable) – The application type.
- **status**: string (default: "open", editable) – Current application status.
- **viewChannels**: array (editable, default: []) – Channels available.
- **name**: string (editable) – Applicant's name.
- **email**: string (required, private, non-editable) – Applicant's email.
- **phone**: string (private, editable) – Applicant's phone number.
- **source**: string (editable) – Where the application comes from.
- **referrer**: string (private, editable) – Who referred the applicant.
- **reviewer_liked**: string (private, editable)
- **adheres**: string (private, editable)
- **fields**: string (editable)
- **inspiration, home, gift, dream**: strings (private, editable)
- **visibility**: enum ("public", "custom", "private", "secret") (default: "public")
- **channel**: string (editable)
- **visibleBy**: array (editable, default: [])
- **reportedBy**: array (default: [])
- **createdBy**: string (default: null)
- **updated, created**: timestamps
- **deleted**: (deletion flag)
- **attributes**: array (default: [])
- **managedBy**: array (default: [])

## Example Requests

### GET Request
```bash
curl -X GET "https://api.closerplatform.org/applications" \
  -H "Authorization: Bearer YOUR_API_KEY"