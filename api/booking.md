# /booking

This model is used for managing bookings, including check-in and check-out dates, status, and other related details.

**Permissions**

* **GET:** Retrieve bookings.
* **POST:** Create new bookings.
* **PATCH:** Update specific fields of a booking.
* **PUT:** Replace an existing booking.
* **DELETE:** Permanently remove a booking from the database.
* **SOFT\_DELETE:** Mark a booking as deleted without permanently removing it from the database.

**Fields**

* **status:** (String, Public, Editable, Default: "open") - Status of the booking.
* **checkin:** (Date, Public, Editable) - Check-in date.
* **checkout:** (Date, Public, Editable) - Check-out date.
* **listing:** (String, Public, Editable) - Listing associated with the booking.
* **description:** (String, Public, Editable) - Description of the booking.
* **message:** (String, Public, Editable) - Message associated with the booking.
* **volunteerId:** (String, Public, Editable) - ID of the volunteer associated with the booking.
* **foodOption:** (Enum, Public, Editable, Default: "no\_food") - Food option. Possible values: "basic", "chef", "no\_food".
* **eventId:** (String, Public, Editable) - ID of the event associated with the booking.
* **eventPrice:** (String, Public, Editable) - Price of the event.
* **eventFiat:** (String, Public, Editable) - Fiat price of the event.
* **eventDiscount:** (String, Public, Editable) - Discount on the event.
* **ticketOption:** (String, Public, Editable) - Ticket option.
* **about:** (String, Public, Editable) - About section for the booking.
* **gift:** (String, Public, Editable) - Gift information.
* **addon:** (Array, Public, Editable) - Add-ons for the booking.
* **start:** (Date, Public, Editable) - Start date.
* **end:** (Date, Public, Editable) - End date.
* **duration:** (String, Public, Editable) - Duration of the booking.
* **adults:** (Integer, Public, Editable) - Number of adults.
* **children:** (Integer, Public, Editable) - Number of children.
* **infants:** (Integer, Public, Editable) - Number of infants.
* **pets:** (Boolean, Public, Editable) - Whether pets are allowed.
* **volunteer:** (String, Public, Editable) - Volunteer information.
* **useTokens:** (Boolean, Public, Editable) - Whether tokens are used.
* **useCredits:** (Boolean, Public, Editable) - Whether credits are used.
* **isDayTicket:** (Boolean, Public, Editable) - Whether it's a day ticket.
* **utilityFiat:** (String, Public, Editable) - Utility fiat amount.
* **utilityToken:** (String, Public, Editable) - Utility token amount.
* **rentalFiat:** (String, Public, Editable) - Rental fiat amount.
* **rentalToken:** (String, Public, Editable) - Rental token amount.
* **dailyUtilityFiat:** (String, Public, Editable) - Daily utility fiat amount.
* **dailyRentalToken:** (String, Public, Editable) - Daily rental token amount.
* **transactionId:** (String, Public, Unique, Editable, Sparse) - Transaction ID.
* **total:** (String, Public, Editable) - Total amount.
* **platformFeeAmount:** (String, Public, Editable) - Platform fee amount.
* **charge:** (String, Private, Editable) - Charge information.
* **paymentIntent:** (String, Private, Editable) - Payment intent information.
* **fields:** (String, Public, Editable) - Custom fields.
* **doesNeedPickup:** (Boolean, Public, Editable, Default: false) - Whether pickup is needed.
* **doesNeedSeparateBeds:** (Boolean, Public, Editable, Default: false) - Whether separate beds are needed.
* **isTeamBooking:** (Boolean, Public, Editable, Default: false) - Whether it's a team booking.
* **paymentDelta:** (String, Public, Editable) - Payment delta.
* **adminBookingReason:** (String, Public, Editable) - Admin booking reason.
* **visibility:** (Enum, Public, Editable, Default: "public", OwnerVisible) - Visibility status of the booking. Possible values: "public", "custom", "private", "secret".
* **channel:** (String, Public, Editable) - The channel to which the booking belongs.
* **visibleBy:** (Array, Public, Editable, Default\
  \
