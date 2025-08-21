Client & Software Requirements
The Gaming Room asked for a modern, multi-platform version of their party game Draw It or Lose It. I designed a client–server web application that supports multiple game rooms, 
teams, and players at once. Key requirements included: unique names for games/teams/players, single authoritative server for game state, simple JSON/REST endpoints, fast updates,
basic authentication/authorization, persistence for games and scores, portability, and ease of deployment.
  
What I Did Well
I think the documentation clearly separates functional vs. non-functional requirements and ties them to design choices. The architecture section shows a simple, scalable REST design.
I also documented core patterns (Singleton for game registry and Iterator for team/player traversal) and included a straightforward data model that enforces name uniqueness.

What Helped When Coding
Writing the design first saved a lot of time. The domain model, API list, and sequence of actions (create game → add team → add player → start round) gave me a checklist to implement.
Deciding up front how errors return (ProblemDetails-style JSON) and how IDs are generated meant less rework during prototyping.

What I Would Revise
I would expand the security and deployment sections: add a short plan for token-based auth, rate limiting, and logging/monitoring, plus a one-page “runbook” for environment variables,
migrations, and rolling updates. I’d also include a brief load-test plan to validate concurrency.

Interpreting & Implementing User Needs
User stories emphasized quick join, no duplicate names, responsive play, and low friction across devices. I implemented these needs by keeping the client thin, 
exposing clear JSON endpoints, centralizing state on the server, and validating uniqueness at the data layer. Considering user needs early avoids UX dead ends 
and keeps technical choices aligned with actual gameplay.

My Design Approach (and Future Strategy)
I started with user stories → requirements → constraints, then chose a simple client–server architecture. From there I drafted the class diagram, data model,
and API contracts, and mapped each requirement to a component. I used light sequence diagrams for tricky flows (room creation, joining, starting a round).
In future projects I’ll follow the same flow, add lightweight ADRs (decision records), and prototype “vertical slices” early to de-risk integration.
