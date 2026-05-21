# MetaMap

**MetaMap** is an open-source, decentralized system designed for the collection, visualization, and collaborative mapping of information. Originally commissioned by an NGO, this platform empowers institutions, universities, and state agencies to deploy their own instances to harness collective intelligence for social good. Use cases range from tracking forest fires to reporting public safety incidents.

This system emphasizes data availability, accountability, and the strict protection of user identities. 

---

## Core Features

### Diverse Data Sources
The system aggregates data from multiple decentralized nodes to ensure high availability.
* **Static Sources:** Supports bulk imports of historical data and public datasets directly via CSV files.
* **Dynamic Sources:** Enables real-time, collaborative uploads of geotagged facts (including text, images, and videos). These contributions can be made by either anonymous or registered contributors.
* **Proxy Sources:** Provides seamless integration with external NGO systems and other MetaMapa instances through REST APIs.
* **Aggregators:** Features dedicated services that combine data from multiple sources. It includes periodic, asynchronous local caching to optimize search speeds and reduce computational costs.

### Collections & Consensus
Administrators can create public Collections that automatically group facts based on configurable inclusion criteria.
* **Navigation Modes:** Users can browse facts in an *unrestricted* mode (all facts) or a *curated* mode (only verified facts).
* **Consensus Algorithms:** To mitigate misinformation, collections utilize algorithms like *Multiple Mentions*, *Simple Majority*, or *Absolute* to weigh the reliability of a fact across different decentralized sources.

### Roles & Accountability
* **Viewers & Contributors:** Users can browse maps, apply filters, and submit new facts without sacrificing their privacy. 
* **Administrators:** Authorized personnel can manage collections, extract statistics, and moderate system content.
* **Moderation & Spam Filtering:** Users can submit deletion requests for sensitive or inaccurate facts. The system includes an automated filter to immediately reject spam requests, leaving valid reports for manual admin review.

### Search & Analytics
* **Full-Text Search:** Includes advanced search capabilities across fact titles and descriptions to ensure users find relevant information even with typos or varied phrasing.
* **Analytics Engine:** Periodically generates system usage statistics, such as facts by province, peak incident hours, and category distributions. All statistics can be exported in CSV format.

---

## Architecture & Technology Stack

MetaMapa is built with a decoupled, scalable architecture focusing on integration and performance:

* **Backend & Persistence:** Built using Java with Hibernate for robust Object-Relational Mapping (ORM) and data persistence, ensuring proper relational modeling and normalization.
* **Web Framework:** Utilizes Javalin to provide a lightweight, efficient foundation for the application's API and web routing.
* **Architecture Pattern:** MVC (Model-View-Controller) leveraging a client-side/server-side interface.
* **Asynchronous Processing:** Heavy use of background, cron-style jobs for managing intensive tasks like aggregations and data syncing.
