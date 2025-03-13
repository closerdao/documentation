---
description: 'Status: Draft, Last Updated: 8 June 2024'
---

# Booking contract

[Proof of Presence (Booking) Contract](https://github.com/closerdao/proof-of-presence) is a framework for using an on-chain lock mechanic to issue utility to a real world asset.

## Functional Requirements

### DAO Membership

* An address must be a DAO member to be able to "instant book"
* If address books without being DAO member, status will be set to "pending" (SPACE\_HOST role would move them to "confirmed")
* _(backlog)_ Upon Check In the Space Host (or DAO approved hardware) changes the booking status to "checked in".&#x20;
* (backlog) Upon cancellation of booking (prior to the booking.start and as defined by DAO rule), contract should return locked tokens to the sender wallet.
* Only an address which has the MEMBERSHIP\_MANAGER\_ROLE, is allowed to add a member to the DAO

## Gherkins

### Add member to DAO

```gherkin
Feature: Add member to DAO

Scenario: Caller has not the right role
	Given the transaction caller **does not** have the right role
	When the DAO contract gets called to add a member
	Then the contract will revert

Scenario: Add member to DAO succesfully
	Given the transaction caller **has** the MEMBERSHIP_MANAGER_ROLE
	When the DAO contract gets called to add a member
	And the member has already been added before
	Then the contract will revert

Scenario: Add member to DAO succesfully
	Given the transaction caller **has** the MEMBERSHIP_MANAGER_ROLE
	When the DAO contract gets called to add a member
	And the member has not already been added before
	Then the address of the new member gets added to the DAO
```

```gherkin
Given 
When
Then
```

## Steps to book

1. Add member to DAO.
   *   Add member to DAO

       Adding a member to the DAO can be done by calling the `addMember()` function.

       **Function:**

       *   addMember(address account)

           **Description**

           Adds a member to the membership registry.

           **Permissions:**

           * Can only be called by an address with the **`AccessControlLib.MEMBERSHIP_MANAGER_ROLE`**

           **Input Validation:**

           * The **`account`** to be added should not already exist in the membership registry
           *   **Technical**

               **Parameters:**

               | Name    | Type    | Description                           |
               | ------- | ------- | ------------------------------------- |
               | account | address | The address of the member to be added |

               **Modifers:**

               | Name                                                 | Description                                                                          |
               | ---------------------------------------------------- | ------------------------------------------------------------------------------------ |
               | onlyRole(AccessControlLib.MEMBERSHIP\_MANAGER\_ROLE) | Ensures the function is called only by an address with the MEMBERSHIP\_MANAGER\_ROLE |

               **Events:**

               *   event MemberAdded(address account, address executer);

                   | Name     | Type    | Description                                        |
                   | -------- | ------- | -------------------------------------------------- |
                   | account  | address | Address of added member                            |
                   | executer | address | Address of membership manager who is adding member |

       **Code:**

       ```jsx
       // New member address
       const memberAddress = "0x..";
       // Create Diamond contract instance
       const DiamondInstance = ...;
       // Call function
       await DiamondInstance.addMember(memberAddress);
       ```

## Booking System Requirements

Aim is to having a booking system as fast

1. anyone with a login can submit a booking request
   * If they are a member and there is space then they get autobooked
2. Member has to be able to cancel their booking
3. CANCELLATION If they cancel the tokens are transferred

