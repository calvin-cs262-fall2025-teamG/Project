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
  | Update Organization   | ✅ | ❌ | ❌ |
  | Transfer Ownership    | ✅ | ❌ | ❌ |
  | Promote to Admin      | ✅ | ❌ | ❌ |
  | Remove Admin          | ✅ | ❌ | ❌ |
  | Remove Members        | ✅ | ✅ | ❌ |
  | Invite Members        | ✅ | ✅ | ✅ |
  | Remove Items          | ✅ | ✅ | ❌ |
  | Add Items             | ✅ | ✅ | ✅ |

  ### User Interface

  ![UI Document](..\UI_Documents\UI_model.png)
  <!-- [UI_Document](UI_Documents\UI_model.jpg) -->

  ![UI Document](..\UI_Documents\UI_new.png)
  <!-- [UI_Document](UI_Documents\UI_model.jpg) -->

  ### Scenarios

  - **User log in** — As a user, I want to be able to create an account so that I can post listed items, personalize my profile, access private items that I have interest in, and securely log in later.
  - **Browse items** — As a borrower, I want to browse the listed items so I can see what I might borrow.
  - **Device type accessibility** — As a mobile user, I want the app to be fully accessible on both iOS and Android devices so that I can use it no matter my phone type.
  - **Privacy** — As a user, I want my personal data/history to be protected so that I feel safe using the app.
  - **Image loading** — As a user browsing multiple items, I want item photos to load quickly and efficiently so that I can see items quickly.
  - **Navigation** — As a first-time user, I want to understand how to navigate the app within 2 minutes without a tutorial so that I can use the app quickly and effectively.
  - **Response time** — As a busy user, I want the app to load pages and search results in under 2 seconds so that I don't waste time waiting.
  - **Bookmark** — As a user, I want to save items I'm interested in so I can revisit them.
  - **Chat** — As a user, I want to chat with the owner of an item so I can ask questions or arrange pickup.
  - **Notified** — As a user, I want to receive updates when items I want are available.
  - **List an item** — As a user, I want to list my own items so I can lend them to others.
  - **Edit item** — As a user, I want to edit my item listings so I can keep them accurate.
  - **Delete item** — As a user, I want to delete my item listings.
  - **Community thread** — As a neighbor, I want to post in a community thread so I can communicate with others nearby.
  - **About us page** — As a new user, I want to see an About Us page so I understand what Hey Neighbor is before signing up.
  - **Multi-neighborhood** — As a user, I want the app to support multiple neighborhoods/communities so I can be in more than one.
  - **Required login** — As a user, I want to be required to log in before browsing so item and borrower/lender info stays private.
  - **Category browsing** — As a user, I want to filter items by a defined category (Books, Tools, etc.) so I can find things faster.

## Ethics
  Hey, Neighbor! is built on the belief that a borrowing network's real value comes from the people in it. It is not just the items members share, but the connections and trust those exchanges create. That principle carries real ethical responsibilities for how the platform is designed and operated.

  **Keeping people at the center**. A borrowing platform only works if the members trust and engage with one another. We must be careful never to design in a way that squeezes people out. That means avoiding barriers, fees, or friction that discourage participation, and not letting a simpler or more impersonal process replace the human interaction that makes the network valuable. Borrowing here is deliberately human to human. Members communicate directly to arrange pickup, ask questions, and build rapport. We must not remove or automate away that personal connection, because it is both the heart of the product and the source of its trust.

  **Avoiding monetization that exploits community trust**. Because the platform is free and community oriented, we should resist pressure to monetize in ways that exploit members' trust or turn neighbors into transactions. Any future revenue model must be transparent, non coercive, and never degrade the borrowing experience or the connections within it.

  **Privacy and personal information**. The platform holds sensitive information, including names, contact details, location, addresses, and borrowing history. Users must be able to control what they share. Personal data should only be used to facilitate borrowing, and it should be protected as the sensitive information it is, in line with the ethical concerns already noted.

  **Trust and fairness**. Because borrowing depends on community governance, owners and admins must not misuse their powers to exclude, punish, or disadvantage members unfairly. Decisions about membership, item removal, and community moderation should be transparent and grounded in the community's own rules.

  **Responsibility and liability**. Lending and borrowing real items carries inherent risks, including theft, damage, and disagreement. While the app does not assume liability, we have an ethical responsibility to make the expectations around lending clear, encourage honest communication, and give members tools to resolve issues fairly.

  **Avoiding harm and waste**. The platform's environmental and community goals, reducing waste and over consumption by sharing rather than buying, should stay central. We should ensure the platform remains genuinely free and accessible, so it serves the community rather than becoming another cost or burden.

  ### Potential Challenges
  - **Privacy & data protection:** we store names, contact details, location,
    and borrowing history. A breach or misuse would harm member trust. Challenge:
    minimize stored data, restrict access, and secure credentials.
  - **Trust & impersonation:** open accounts mean fake or unverified members could
    join. Challenge: how to verify identity without adding friction.
  - **Abuse of moderation power:** owners/admins could unfairly exclude or punish
    members. Challenge: keep membership and moderation decisions transparent.
  - **Liability and disputes:** items can be damaged or not returned. We don't
    assume liability, so the challenge is setting clear expectations and giving
    members fair ways to resolve disagreements.
  - **Monetization pressure:** staying free and community-based invites pressure
    to monetize. Challenge: resist models that exploit trust or degrade the
    experience.

## Development Process

We will use GitHub Flow for version control. All work happens on feature
branches (e.g., `feature/community-chat`), reviewed via pull requests before
merging into `main`. Each PR requires at least one team member review.

- **Team meetings:** Thursday nights (weekly) 4-6 pm to sync progress and assign work.
- **Advisor check-ins:** every Tuesday with our advisor.
- **Individual work:** each member commits ~3 hours of solo work per week.
- **Tooling:** ticketed tasks tracked in the repo's issue tracker; features
  merged via PR; CI runs tests on every pull request.

Because several features remain in active development, we keep branches short-lived
and merge frequently to avoid long-lived, hard-to-review changes.
  
## Results

This section assesses the current state of Hey, Neighbor! against the goals and success criteria defined in the earlier sections of this report.


### Work Still In Progress
The remaining changes from this year's scope — the **community chat thread**, **community discovery and membership**, **shared image storage**, and the **expanded profile settings** — are under active development and not yet complete.

### Testing Status
Because several features remain in progress, full end-to-end validation has not yet been completed. The finished account and authentication features have been verified to work within the community-based flow. The remaining features will be validated against the success criteria as they are completed.

### What Success Will Look Like
We will consider the overall project a success if, once the remaining features are complete, users can reliably create and join communities, request and share items entirely through human-to-human communication, and trust that their data stays protected — all without the scope expanding beyond the stated non-goals.

## Conclusion

Hey, Neighbor! has laid the groundwork last year for its transition from a Calvin-only campus app to a community-based borrowing platform serving churches, neighborhoods, schools, and other trusted groups. The completed open account system and hardened route authentication provide the secure base that all of this year's remaining features build upon.

The features still in progress — community chat, discovery and membership, shared image storage, and expanded profile settings — represent the bulk of the user-facing change. Once finished and validated, Hey, Neighbor! will deliver on the vision set out in its objective: a free, peer-to-peer borrowing network built around communities whose members already share a basis for trust, offering value that neither buy-and-sell marketplaces nor fee-based rental services can match. Success for this year's project therefore depends less on the work already done and more on completing and validating the community features that remain.

## Development Process

We use a Github feature-branch workflow: changes are made on individual branches and merged into main via pull request after review by a teammate.

We track tasks on Trello, organized into back-log/doing/done sprint cards.

We meet as a team weekly on Thursdays at 4pm and with our advisor, Professor Norman, weekly on Tuesdays at 2:30pm. Outside of meetings, each team member puts in roughly 3 hours of independent work per week, adjusted based on how long Thursday's meeting runs.

Our goal is to have the app feature-complete by January, so that spring semester can focus on user testing (ideally with a real community, such as a local church, using the app and giving us feedback.)