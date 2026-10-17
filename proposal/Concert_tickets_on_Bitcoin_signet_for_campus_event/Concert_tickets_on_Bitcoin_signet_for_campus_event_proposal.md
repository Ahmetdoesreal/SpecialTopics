# Concert tickets on Bitcoin signet for campus events

SEN0401 Special Topics: Blockchain · 2026-2027 Fall · Proposal · Method: BRSF software-development profile · Self-assessed grade 97.6/100

## Team, roles and work distribution

| Member | Student number | E-mail | Administrative roles | Development roles | Planned share |
| --- | --- | --- | --- | --- | --- |
| Mert Özek | 2300007579 | 2300007579@stu.iku.edu.tr | Team lead | Architect, Back-end developer | 15% |
| Göktuğ Güncer | 2300006211 | 2300006211@stu.iku.edu.tr | Customer liaison | Front-end developer, Data engineer, Knowledge engineer | 14% |
| İrem Ayranpınar | 2300005623 | 2300005623@stu.iku.edu.tr | Documentation lead | Front-end developer, Interaction and game designer | 14% |
| Oğuzhan Kaya | 2200004591 | 2200004591@stu.iku.edu.tr | Process facilitator | Smart-contract developer, Back-end developer | 14% |
| Semih Canik | 2200008618 | 2200008618@stu.iku.edu.tr | Work-log steward | Front-end developer, Interaction and game designer | 14% |
| Sıla Özer | 2300005208 | 2300005208@stu.iku.edu.tr | Quality lead | Front-end developer, Interaction and game designer | 14% |
| Ahmet Deniz Sezgin | 2300005633 | 2300005633@stu.iku.edu.tr | Repository and release manager | Back-end developer, Release and operations | 15% |

### Modules and features

| Module or feature | Kind | What it does | Delivers epic | Responsible member | Second member |
| --- | --- | --- | --- | --- | --- |
| Ticket API | Module | Event and ticket APIs, transfer rules and gate signature checks. Mert defines the OpenAPI format and JSON examples with the team. He uses mock data and chain services while others build them. In week one, the team connects event creation, wallet display and a gate result with sample data. The owner adds tests, a short guide and a demo. The backup reviews changes and can take over. | Hold and transfer tickets on signet | Mert Özek · 2300007579 | Ahmet Deniz Sezgin · 2300005633 |
| Data services and releases | Module | Oxigraph storage, ownership records, atomic check-in, report queries, CI and releases. Deniz agrees on data interfaces with Mert and starts with sample records. They share backend integration work. Everyone starts together, uses separate branches and merges small reviewed changes. Real services replace mocks as they become ready. The owner adds tests, a short guide and a demo. The backup reviews changes and can take over. | Hold and transfer tickets on signet | Ahmet Deniz Sezgin · 2300005633 | Mert Özek · 2300007579 |
| Organiser frontend | Feature | Event form, organiser panel, minting screen and API connections. Irem starts with mock API responses and simple local UI components. Her frontend workload is similar to Sila's. Goktug builds the report screen separately. The owner adds tests, a short guide and a demo. The backup reviews changes and can take over. | Create events and issue tickets | İrem Ayranpınar · 2300005623 | Sıla Özer · 2300005208 |
| Gate scanner frontend | Feature | QR challenge flow, entry results, offline-cache screens and API connections. Sila uses simulated valid, copied and used tickets. Her frontend workload is similar to Irem's. She agrees on challenge messages with Semih and Mert. Mert checks signatures; Deniz stores entry records. The owner adds tests, a short guide and a demo. The backup reviews changes and can take over. | Check ticket ownership at the gate | Sıla Özer · 2300005208 | Göktuğ Güncer · 2300006211 |
| Report frontend and data model | Feature | Split work roughly equally between report screens/shared UI components and JSON-LD/SHACL data models. Goktug starts with sample reports and valid/invalid records. Later, the report reads Deniz's queries through Mert's API. The owner adds tests, a short guide and a demo. The backup reviews changes and can take over. | Create events and issue tickets | Göktuğ Güncer · 2300006211 | İrem Ayranpınar · 2300005623 |
| Phone wallet | Feature | Wallet keys, ticket display, transfers, challenge signing and ticket collection. Semih starts with sample tickets and mock replies. He agrees on challenge messages with Sila and Mert. Semih and Oguzhan review the wallet/chain connection and learn to run each other's modules. The owner adds tests, a short guide and a demo. The backup reviews changes and can take over. | Hold and transfer tickets on signet | Semih Canik · 2200008618 | Oğuzhan Kaya · 2200004591 |
| Blockchain service | Module | Ticket script, time lock, minting, PSBT signing, signet node and club wallet. Oguzhan agrees on the chain interface with Mert and Semih. He tests transactions independently on regtest before signet. Semih and Oguzhan are each other's backups. The owner adds tests, a short guide and a demo. The backup reviews changes and can take over. | Hold and transfer tickets on signet | Oğuzhan Kaya · 2200004591 | Semih Canik · 2200008618 |

### Process leads

- Mission analysis: Semih Canik
- Stakeholder needs and requirements: Göktuğ Güncer
- System/software requirements definition: İrem Ayranpınar
- Architecture definition: Mert Özek
- Design definition: İrem Ayranpınar
- System analysis: Göktuğ Güncer
- Implementation: Oğuzhan Kaya
- Integration: Mert Özek
- Verification: Sıla Özer
- Transition: Ahmet Deniz Sezgin
- Validation: Sıla Özer
- Operation: Oğuzhan Kaya
- Maintenance: Ahmet Deniz Sezgin
- Disposal: Semih Canik

### Work log

0 entries; chain intact; head fingerprint none.

## 1. Mission

### Customer

| Customer (organisation or role) | Contact person or role | How and when you reached them | Relation | What they get from it |
| --- | --- | --- | --- | --- |
| Campus music club | Assumed contact: club events coordinator. | Not contacted yet. First meeting planned for the week of 2026-10-26. | Owner of the system | Tickets with ownership checks, resale limits and quick entry. |

### End users

| User group (short name) | Who exactly | What they do with the system | How often | Device or channel |
| --- | --- | --- | --- | --- |
| Event organiser | Club members who organise concerts. | Create events, set ticket rules and issue tickets. | three to four events a term | laptop browser |
| Ticket holder | Students and guests attending concerts. | Keep, transfer and show tickets on a phone. | a few events a term | phone |
| Gate staff | Club volunteers at the entrance. | Scan tickets and admit valid holders. | Each event, a few hundred scans per hour | phone |

### Problem

The club runs three to four concerts each term for about 300 people. Tickets are sold through messages, bank transfers and a spreadsheet. Buyers receive QR ticket images, which are easy to copy and share. About 40 copied tickets were found at the last spring concert. Some tickets are resold for two to three times their original price. At the entrance, staff check names manually. Each check takes about 30 seconds, and queues can last 45 minutes. These problems make entry slow and create confusion for buyers and staff. Buyers need a simple way to prove ticket ownership, transfer tickets safely to friends when plans change, and keep their tickets as memories after the concert without relying on copied images. The club also needs clear and reliable records of each ticket transfer.

### Mission statement

Help event organisers issue concert tickets on Bitcoin signet. Let each ticket holder prove ownership at the gate, transfer tickets at or below the original price with club approval, and keep them after the event. Help gate staff reject copied or used tickets and manage entry more easily.

Origin: Session drafted

### Outcome

Gate staff can check an unused ticket within two seconds. The system rejects copied or used tickets and transfers above the original price. Ticket holders can keep tickets from attended events in their collection.

## 2. Scope

### Areas

| Area | Where it lives | How big it is today |
| --- | --- | --- |
| Event and ticket records | model/ and shapes/ | Only a spreadsheet today. |
| Ticket tokens on signet | chain/ | No tokens today. |
| Holder wallet and gate check | web/ | QR images and a name list today. |

### Deliverables

| Deliverable | Area | Layer | Kind |
| --- | --- | --- | --- |
| schema.org event, offer and ticket records in JSON-LD, with SHACL resale rules. | Event and ticket records | Product layer | Functional |
| Organiser page to create events and explain invalid rules. | Event and ticket records | Product layer | Functional |
| Signet ticket script, minting and club-approved transfers. | Ticket tokens on signet | Product layer | Functional |
| Keep personal data off the chain. | Ticket tokens on signet | Product layer | Non-functional |
| Phone wallet with ticket transfers and a collection. | Holder wallet and gate check | Product layer | Functional |
| Gate scanner with signed challenges and results in under two seconds. | Holder wallet and gate check | Product layer | Functional |

### Exclusions

| Left out | Why |
| --- | --- |
| Mainnet transactions and real bitcoin | Use signet only, with no real bitcoin. |
| Taking ticket payments | The club collects lira payments separately. |
| Stopping payments made outside the system | The system cannot check cash or other outside payments. It uses the price both sides confirm. |
| Seat maps and reserved seating | Use standing events with one ticket type. |

### Domain entities

| Entity | What it is | Created? | Used? | Retired? |
| --- | --- | --- | --- | --- |
| Event | A schema:MusicEvent with date, venue, capacity and resale rules. | Created — yes | Used — yes | Retired — no |
| Ticket | A schema:Ticket identified by its mint transaction output. | Created — yes | Used — yes | Retired — no |
| Ticket output | The current unspent output, locked to holder and club keys. | Created — yes | Used — yes | Retired — yes |
| Transfer | A signet transaction that changes the holder with club approval. | Created — yes | Used — yes | Retired — no |
| Check-in | An entry record based on a signed gate challenge. | Created — yes | Used — yes | Retired — no |

### Project kinds

Knowledge-graph application › Graph-backed web application; Provenance and trust. Stack layers they need: Data model, Query, Storage and serving, Identifiers and publishing, Provenance and metadata.

### Semantic technologies, by stack layer

- Data model: RDFLib
- Governance and compliance: KVKK personal-data regime
- Identifiers and publishing: Stable IRI and negotiation practice
- Provenance and metadata: PROV-O provenance ontology
- Query: SPARQL 1.1 and 1.2
- Serialisation: JSON-LD 1.1 contexts, RDFLib
- Storage and serving: Oxigraph
- Validation: SHACL shapes, pySHACL
- Vocabularies and taxonomies: schema.org

Use schema.org and JSON-LD for event and ticket records. RDFLib handles these records in Python. SHACL and pySHACL check required fields and resale rules. Oxigraph stores records; SPARQL reads collections and reports. PROV-O tracks ticket creation and transfers. Stable IRIs identify tickets. Keep personal data off the chain for privacy.

## 3. Goals

| Goal | Facing | Covers area | Why this goal |
| --- | --- | --- | --- |
| Admit only holders of unused tickets | Mission-facing | Holder wallet and gate check | Reduce copied tickets and queues. |
| Keep valid event and ticket records | Scope-facing | Event and ticket records | Transfers and collections need correct data. |
| Issue and transfer tickets under club rules | Scope-facing | Ticket tokens on signet | Prevent transfers that break the resale rules. |
| Keep personal data off the chain | Containment-facing | Ticket tokens on signet | Protect holder privacy. |

### Specification

The organiser creates an event with a capacity, price and resale rules. SHACL checks these records. Each ticket is a signet output that needs both holder and club signatures. One week after the event, the holder can spend it alone. The phone wallet stores the holder's key. The club approves transfers only at or below the original price and allows at most three transfers. At the gate, the wallet signs a fresh challenge. The service checks ownership and whether the ticket was already used. Tickets remain in the holder's collection after the event.

### Test scenarios

| Kind | Scenario (Given / When / Then) |
| --- | --- |
| Nominal | Given an unused ticket, when its wallet signs the gate challenge, then admit the holder within two seconds and record entry. |
| Rejection | Given a copied ticket image, when it is scanned without the holder's key, then reject it and show a reason. |
| Rejection | Given a transfer price twice the original price, when approval is requested, then refuse it and keep the current holder. |
| Boundary | Given three previous transfers, when a fourth is requested, then refuse it and explain the limit. |

### Use cases

Organiser: create events, issue tickets and view reports. Holder: receive, transfer, show and collect tickets. Gate staff: scan tickets and admit holders.

## 4. Objectives

| Objective | Goal | Measured by | How exactly it is measured | Now | Target | Direction |
| --- | --- | --- | --- | --- | --- | --- |
| Invalid tickets admitted | Admit only holders of unused tickets | Counted | Number of copied or invalid tickets admitted per event. | 40 | 0 | Decrease |
| Valid event and ticket records | Keep valid event and ticket records | Counted | Percentage of records passing SHACL checks. | 0 | 100 | Increase |
| Transfers following the rules | Issue and transfer tickets under club rules | Counted | Percentage of signet transfers with club approval and a confirmed price at or below the original price. | 0 | 100 | Increase |
| Personal data on chain | Keep personal data off the chain | Counted | Number of outputs or witnesses containing data other than keys, signatures and the ticket script. | 0 | 0 | Hold |

### Activity model

Create and validate the event. Mint one ticket output per place and save its ID. After payment, assign the ticket to the buyer's wallet key. For a transfer, both sides confirm the price and the club checks the rules. At the gate, verify the wallet signature and record entry.

### Sequence model

The organiser page sends an event to TicketAPI. The service validates it with pySHACL and stores it in Oxigraph. Bitcoin Core funds and signs the mint transaction. For transfers, the wallet signs a PSBT; the service checks the rules, adds the club signature and fee input, then broadcasts it. At the gate, the wallet signs a fresh nonce. The service checks ticket ownership and previous entry.

## 5. Backlog

Kind of development: Initial development

### Epics

| Epic | Pursues objective |
| --- | --- |
| Create events and issue tickets | Valid event and ticket records |
| Hold and transfer tickets on signet | Transfers following the rules |
| Check ticket ownership at the gate | Invalid tickets admitted |

### Stories

| Epic | As a | I want | So that | Acceptance (Given / When / Then) | Category | Design concern | Value 1–10 | Time 1–10 | Risk 1–10 | Size 1–10 | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Create events and issue tickets | Event organiser (end user) | to set an event's capacity, price and resale cap | ticket rules are clear from the start | Given a complete event form When I save it Then a valid schema.org MusicEvent with an IRI is stored | New capability | Data | 8 | 6 | 6 | 4 | 5 |
| Create events and issue tickets | Event organiser (end user) | to issue all event tickets at once | ticket sales can start | Given an event with capacity 300 When I mint tickets Then one signet transaction creates 300 ticket outputs and each ticket has a page | New capability | Architecture | 9 | 7 | 7 | 6 | 3.8 |
| Hold and transfer tickets on signet | Ticket holder (end user) | to receive tickets in a browser wallet | I can prove ownership without a separate app | Given a ticket assigned to my key When I open the wallet Then it shows the event, my ownership and unused status | New capability | User interface | 9 | 6 | 5 | 5 | 4 |
| Hold and transfer tickets on signet | Ticket holder (end user) | to transfer my ticket at the original price | a friend can use it if I cannot attend | Given an unused ticket priced at or below its original price When both holders confirm Then the club co-signs and the new holder receives it | New capability | Security | 10 | 7 | 9 | 8 | 3.3 |
| Check ticket ownership at the gate | Gate staff (end user) | to check a ticket within two seconds | people enter quickly | Given an unused ticket When its wallet signs the scan challenge Then the scanner shows green and records entry | New capability | Interaction | 10 | 9 | 8 | 6 | 4.5 |
| Check ticket ownership at the gate | Gate staff (end user) | to reject copied or used tickets clearly | I can explain why entry is refused | Given a used ticket When it is scanned again Then the scanner shows red and the first entry time | New capability | Security | 9 | 8 | 9 | 3 | 8.7 |
| Check ticket ownership at the gate | Ticket holder (end user) | to keep tickets after concerts | I can see the events I attended | Given tickets used at past events When I open my collection Then each shows the event date and an attended badge | New capability | User interface | 6 | 3 | 3 | 3 | 4 |
| Create events and issue tickets | Campus music club (customer) | to view an event report | the club can see ticket use and transfers | Given a finished event When I open its report Then a SPARQL query shows issued, transferred and used ticket counts | New capability | Interface | 5 | 3 | 4 | 2 | 6 |

### Definition of done

| Criterion | How it is checked |
| --- | --- |
| All automated tests pass | GitHub Actions on every push. |
| Stored events and tickets pass SHACL checks | Run pySHACL in service tests. |
| Ticket spending follows the script rules | On regtest, test joint signatures, holder-only spending after the time lock and rejection before it. |
| No personal data appears on chain | Decode all test outputs and witnesses. |

### Class model

Event stores the date, venue, capacity and ResaleRule. The rule stores the price, resale cap and transfer limit. Ticket belongs to one Event and uses its mint outpoint as its ID. TicketOutput stores the current outpoint, holder key and script. Transfer links old and new outputs, price and club signature. CheckIn records the ticket, time and gate device. Each ticket has one current unspent output.

### Test cases

| For story | Test case | Test data |
| --- | --- | --- |
| to set an event's capacity, price and resale cap | Accept a complete event. Reject a resale cap above its price. | two synthetic events |
| to issue all event tickets at once | Mint 300 signet tickets and read back their output IDs. | one valid event and a funded signet wallet |
| to receive tickets in a browser wallet | Assign a ticket to a wallet key and view it on a phone screen. | one minted ticket |
| to transfer my ticket at the original price | Accept a transfer at the original price. Reject twice that price. | one ticket and two wallets |
| to check a ticket within two seconds | Scan an unused ticket and measure response time. | one unused ticket in a wallet |
| to reject copied or used tickets clearly | Reject a copied QR and a second scan of a used ticket. | one ticket, one copied QR image |
| to keep tickets after concerts | Check in at two events, then view both in the collection. | two synthetic events with check-ins |
| to view an event report | Compare SPARQL report totals with manual counts. | one synthetic event with 50 tickets, 10 transfers and 40 check-ins |

### Architecture — Component diagram

A Python ticket service uses Oxigraph and a Bitcoin Core signet node over RPC. The club key stays in the service. Static web pages provide the organiser panel, wallet and scanner. Node settings and keys are configurable.

### Data — Class diagram

Event uses schema:MusicEvent. Ticket uses schema:Ticket and prov:Entity. Transfer uses prov:Activity. ResaleRule, TicketOutput and CheckIn complete the model. EventShape, ResaleRuleShape and TransferShape validate the records.

### Interaction — Sequence diagram

The scanner shows a QR challenge. The wallet scans and signs it, then shows a reply QR. The scanner reads the reply, checks with the service and shows the result.

### Interface — Component diagram

The organiser panel, wallet and scanner call TicketAPI. TicketAPI uses the Oxigraph store, pySHACL validator and chain service. The chain service holds the club key and calls Bitcoin Core over RPC.

### Security — State machine diagram

Before the time lock ends, spending needs holder and club signatures. One week after the event, the holder can spend alone. Ticket states are minted, assigned, transferred, checked in and souvenir. Each ticket can be checked in once. Each challenge nonce is used once.

### User interface — design model

The wallet shows ticket cards with event, date, status, transfer and gate buttons. The scanner shows a large green or red result with a reason. Both screens must be readable on a phone in a dark hall.

## 6. Course-specific

### Blockchain design

Use Bitcoin Core on signet. Each ticket is a P2WSH output requiring holder and club signatures. OP_CHECKLOCKTIMEVERIFY allows the holder to spend alone one week after the event. The mint outpoint identifies the ticket. Transfers move it to output 0 of the next transaction, preserving its history. The wallet signs a PSBT; the club checks the price, co-signs and adds the fee input. The chain records ownership outside the club database. After the time lock, the holder can control the souvenir without the club.

## Plan and risks

| Date | Deliverable | Lead |
| --- | --- | --- |
| 2026-10-30 | Data model, SHACL checks, sample records and a report screen prototype. | Göktuğ Güncer |
| 2026-10-30 | Organiser panel and minting screen with mock API responses and UI tests. | İrem Ayranpınar |
| 2026-11-20 | Ticket API and rule checks, tested and connected to available services. | Mert Özek |
| 2026-11-20 | Signet minting and transfers, with regtest checks and wallet examples. | Oğuzhan Kaya |
| 2026-12-04 | Wallet, transfers, challenge signing and collection ready for a mock event. | Semih Canik |
| 2026-12-04 | Gate scanner ready for a mock event; tests for valid, copied and used tickets. | Sıla Özer |
| 2026-12-18 | Data services and reports in the final release. Deniz coordinates packaging; everyone supplies tests and guides. Interfaces and sample data are shared in week one, with integration throughout the project. | Ahmet Deniz Sezgin |

| Risk | Likelihood | Impact | Mitigation |
| --- | --- | --- | --- |
| A holder loses their phone or wallet key. | Medium | Medium | Show backup words at setup. Plan a club reissue process before the event and mark the old ticket void. |
| Weak internet slows gate checks. | Medium | High | Cache unspent tickets before the event, check signatures offline and sync entry records later. |
| Buyers pay extra outside the system. | High | Medium | Limit transfers to three, require a confirmed price and flag unusual transfer histories. |
| Not enough signet coins to mint tickets. | Medium | Medium | Fund the wallet early, use small outputs and run automated tests on regtest. |

Repository: https://github.com/Ahmetdoesreal/SpecialTopics — Confirmed on GitHub 2026-10-17 (public, created 2026-10-09)

## References

1. Antonopoulos, A. M. (2017). Mastering Bitcoin, 2nd ed. O'Reilly. Chapters 4 (Keys, Addresses), 6 (Transactions) and 7 (Advanced Transactions and Scripting).
2. Nakamoto, S. (2008). Bitcoin: A Peer-to-Peer Electronic Cash System.
3. Todd, P. (2014). BIP 65: OP_CHECKLOCKTIMEVERIFY. Bitcoin Improvement Proposals.
4. Chow, A. (2017). BIP 174: Partially Signed Bitcoin Transaction Format. Bitcoin Improvement Proposals.
5. Lombrozo, E., Lau, J. & Wuille, P. (2015). BIP 141: Segregated Witness. Bitcoin Improvement Proposals.
6. Alm, K.-J. (2019). BIP 325: Signet. Bitcoin Improvement Proposals.
7. schema.org: MusicEvent, Offer and Ticket types, https://schema.org
8. W3C (2017). Shapes Constraint Language (SHACL). W3C Recommendation.
9. W3C (2020). JSON-LD 1.1. W3C Recommendation.
10. Law No. 6698 on the Protection of Personal Data (KVKK), Türkiye.

## Self-assessment

| Part | Weight | Grade | Criteria met |
| --- | --- | --- | --- |
| Team and work | 10% | 76/100 | 10 of 12 |
| Mission | 20% | 100/100 | 7 of 7 |
| Scope | 15% | 100/100 | 8 of 8 |
| Goal | 15% | 100/100 | 7 of 7 |
| Objective | 10% | 100/100 | 3 of 3 |
| Backlog | 20% | 100/100 | 10 of 10 |
| Course-specific | 5% | 100/100 | 1 of 1 |
| Plan and references | 5% | 100/100 | 3 of 3 |
| Overall | 100% | 97.6/100 |  |

### Member grades (Proposal)

Project grade 100 (60%), team grade 76 (20%), individual contribution (20%).

| Member | Student number | Individual | Member grade |
| --- | --- | --- | --- |
| Mert Özek | 2300007579 | 22 | 79.6 |
| Göktuğ Güncer | 2300006211 | 22 | 79.6 |
| İrem Ayranpınar | 2300005623 | 22 | 79.6 |
| Oğuzhan Kaya | 2200004591 | 22 | 79.6 |
| Semih Canik | 2200008618 | 22 | 79.6 |
| Sıla Özer | 2300005208 | 22 | 79.6 |
| Ahmet Deniz Sezgin | 2300005633 | 22 | 79.6 |

