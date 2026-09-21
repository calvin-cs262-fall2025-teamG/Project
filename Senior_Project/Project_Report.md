# Hey Neighbor Mobile Application

## Objective
  Hey, Neighbor! gives communities like churches, neighborhoods, and schools an easy way to borrow and lend items they rarely use, like tools, camping gear, and household equipment, within a trusted network. Rather than people buying their own rarely-used items, members can rely on what their community already owns, reducing waste, cutting costs, and forming neighborly connections.

  Unlike Facebook Marketplace, which is built around buying and selling rather than borrowing, or rental services like Yoodilize, which charge fees and are not strictly community-based, Hey, Neighbor! offers a free, peer-to-peer platform that combines the convenience of a rental service with the trust of a neighborhood network. This makes Hey, Neighbor! not just practical, but valuable for any community it serves.

## Background

Hey, Neighbor! began as a project in Calvin's CS 262 course, built by Bryn Lamppa, Rose Campbell, Maham Abrar, Beta Akari, and Simon Willover. At that stage, the app was Calvin-oriented, with a hope of eventually expanding beyond just Calvin campus. Listed items consisted mostly of things students would need temporarily and didn’t want to buy outright, like textbooks, calculators, and dorm supplies.

The CS 262 version was a simple, straightforward browsing app. Users could look through items other students had listed, each with a description, a profile of the person lending it, an in-app chat, and a borrow button. The borrow button simply notified the lister that someone was interested. The actual details of pickup and how long the item would be borrowed for were left to the two users to work out over chat. A bookmarking feature that lets users save items they were interested in or that were already being borrowed. The app had five tabs: home, search, list, chat, and profile.

On the technical side, the CS 262 version consisted of a React Native (Expo) mobile client, a Node.js/Express backend, and a PostgreSQL database, deployed on Microsoft Azure. Account sign-up was gated to Calvin email addresses having the application restricted to Calvin University students only.

### This Year's Work:
This year's project returns Hey, Neighbor! to the goal the original CS 262 team hoped for but did not build. A community-based borrowing app, rather than one limited to a single campus. Instead of only Calvin students, users will be able to create or join a trusted network of individuals, a church, a neighborhood, a school, or any other group, and lend and borrow items within it. The kinds of items expected to be shared now will be shifted towards household or outdoor items like power drills, camping gear, weed wackers, etc.

#### Current Changes and Implementations:
- Account creation moves from Calvin email sign-up to a standard email and password account open to anyone.
- The Search tab is being replaced by a community chat thread, where users can post and browse requests for items they need, rather than only browsing what has already been listed.
- Community discovery and membership are being added. Users will be able to explore communities beyond the ones they already belong to and request to join, with the community's owner able to approve or deny that request.
- Image storage is being moved to a more reliable, shared solution, rather than files saved locally.
- Route authentication is being made more secure.
- Profile settings are being expanded beyond just name and profile picture, to include account deletion, password changes, logout, and email changes.

### Competing and Related Products:
**Facebook Marketplace:** Facebook Marketplace is a buying and selling platform built into Facebook that lets users post items for others to buy, or buy items others have posted. It is similar to Hey, Neighbor! in that it connects nearby individuals directly, but it differs in that it is not free. It facilitates actual purchases rather than borrowing, and it is not strictly community-based. Any two users within a broad geographic radius can transact regardless of whether they share any other connection.

**Yoodlize:** Yoodlize is a rental platform that allows people to rent items from one another. Unlike Hey, Neighbor!, it is not free. Yoodlize charges a commission on each transaction, and renters pay for the time they use an item.

**Buy Nothing Project:** The Buy Nothing Project is a nonprofit gift economy where members of a local community can give away or request items for free. It is closer to Hey, Neighbor! than the previous two products in that it is free and community-oriented, but it differs in that it is a pure gift economy. Items are given away permanently rather than borrowed and returned. Membership is also geographically gated to a single group per area, opposed to multiple, user-created communities Hey, Neighbor! is built around.

Hey, Neighbor! is unique in that it is simultaneously free, structured around borrowing and returning rather than buying or gifting, and built specifically around communities whose members already share a basis for trust, with the flexibility for users to belong to and move between multiple such communities.

**Works Cited**

“BNProject | About Us.” *Buynothingproject.Org*, https://buynothingproject.org/about. Accessed 21 Sept. 2026.

“How Marketplace Works | Facebook Help Center.” *Www.Facebook.Com*, https://www.facebook.com/help/1889067784738765. Accessed 21 Sept. 2026.

“Yoodlize: Rent Anything From Anyone.” *Yoodlize.Com*, 2025, https://www.yoodlize.com/.

## Normative and Ethical Considerations
  - Personal Information
    - Name, Age, Address, Phone #, ect
  - Theft
  - Damage

## Success Criteria
  ### Goals
    - Users can request and share various items within communities.
    - Users can create and join communities.
    - Users can message communities to request items.
    - Users can post available items within their community.
    - Users can browse and request to join communities.
    - Borrowing requires human to human communication.
    - Users can promote members to "Admin" to regulate communities.
    - Users will be able to request an item within their communities.
    - Users can see borrowed statistics of their posted items.
  ### Non-Goals
    - Users can only borrow items within a community.
    - Users will not be rated.
    - We will not handle item liability.
    - Items cannot be listed on specific communities. 
      - All items will be listed on all communities.

## Approach and Implementation
  ### User Roles
  | Management Privilege  | Owner | Admin | Member |
  | --------------------- | ----- | ----- | ------ |
  | Delete Organization   | ✅ | ❌ | ❌ |
  | Rename Organization   | ✅ | ❌ | ❌ |
  | Transfer Ownership    | ✅ | ❌ | ❌ |
  | Promote to Admin      | ✅ | ❌ | ❌ |
  | Remove Admin          | ✅ | ❌ | ❌ |
  | Remove Members        | ✅ | ✅ | ❌ |
  | Invite Members        | ✅ | ✅ | ✅ |
  | Remove Items          | ✅ | ✅ | ❌ |
  | Add Items             | ✅ | ✅ | ✅ |

  ### User Interface
  Needs some tweaking, prob should be individual screens and formatted better, im just lazy rn and want to have the section

  ![UI Document](..\UI_Documents\UI_model.jpg)
  <!-- [UI_Document](UI_Documents\UI_model.jpg) -->

  ### Scenarios
  Basically user stories (idk where you put those I didn't see them on trello)
  
## Results

## Conclusion