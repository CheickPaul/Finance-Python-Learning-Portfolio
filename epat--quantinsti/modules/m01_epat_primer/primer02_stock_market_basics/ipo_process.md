### IPO Process — Roles & Steps

```mermaid
flowchart TD

%% --- Swimlanes / actors ---
subgraph C0[Company]
  C1[Decide to go public]
  C2[Draft prospectus]
  C3[Post IPO<br/>ongoing disclosures]
end

subgraph U0[Underwriters]
  U1[Select advisors]
  U2[Valuation<br/>price range]
  U3[Investor education<br/>roadshow]
  U4[Book building<br/>collect demand]
  U5{Underwriting model}
  U5a[Firm commitment<br/>bank buys then resells]
  U5b[Best efforts<br/>bank places no purchase]
  U5c[Other models<br/>all or none mini maxi<br/>direct listing]
  U6[Pricing and allocation]
  U7[Stabilization<br/>Greenshoe]
end

subgraph R0[Regulator]
  R1[Regulatory review<br/>approval]
end

subgraph X0[Exchange / CCP]
  X1[Listing on exchange<br/>first day of trading]
  X2[Settlement and delivery<br/>T plus 2]
end

subgraph I0[Investors]
  I1[Subscribers and<br/>secondary buyers]
end

%% --- Main flow with a few edge labels ---
C1 -->|mandate| U1
U1 --> C2
C2 -->|file| R1
R1 --> U2
U2 --> U3 --> U4 --> U5
U5 --> U5a --> U6
U5 --> U5b --> U6
U5 --> U5c --> U6
U6 --> X1 --> U7 --> X2 --> C3

%% investors connect at primary and secondary stages
I1 --- U4
I1 --- X1

%% --- Explanatory callouts (short and wrapped, no parentheses/dashes) ---
Kx[Greenshoe up to 15 percent extra shares<br/>used by underwriters to stabilize price]
Tx[T plus 2 cash and shares delivered<br/>two business days after trade<br/>via clearing and settlement]
Lx[Post IPO lock ups for insiders 90 to 180 days<br/>plus periodic financial reports]

U7 -.-> Kx
X2 -.-> Tx
C3 -.-> Lx
```
### IPO Process — Message Flow (Sequence)
```mermaid
sequenceDiagram
  participant Co as Company
  participant UW as Underwriters
  participant Reg as Regulator
  participant Ex as Exchange CCP
  participant Inv as Investors

  Co->>UW: 1 Decide to go public
  Co->>UW: 2 Select advisors and mandate
  UW-->>Inv: 3 Map investors universe

  Co->>UW: 4 Draft prospectus start
  UW->>Reg: 5 File to regulator
  Reg-->>Co: 5 Review and approval cycle

  UW->>Co: 6 Valuation and price range
  UW->>Inv: 7 Roadshow and education
  UW->>Inv: 8 Book building collect orders

  UW->>Co: 9 Underwriting model
  alt 9a Firm commitment
    UW->>Co: Banks buy issue then resell
  else 9b Best efforts
    UW->>Co: Banks place issue no purchase
  else 9c Other models
    UW->>Co: All or none or mini maxi or direct listing
  end

  UW->>Inv: 10 Pricing and allocation
  Co->>Ex: 11 List shares first day trading
  UW->>Ex: 12 Stabilization Greenshoe if used
  Inv->>Ex: Secondary trading
  Ex->>Ex: 13 Settle and deliver T plus 2
  Co-->>Inv: 14 Post IPO lock ups and ongoing disclosures
  ```

### IPO Step Details (Reference Table)

| # | Step | Who | What happens | Key outputs/docs | Notes / Risks |
|---|---|---|---|---|---|
| 1 | Decide to go public | Company, board | Go/no-go decision, timeline, readiness check | Board approval | Market window, governance readiness |
| 2 | Select advisors | Company → Underwriters; legal; auditors | Mandate bookrunners, kick-off, open data room | Engagement letters, timetable, working group list | Pick banks with sector strength/distribution |
| 3 | Map investors universe | Underwriters | Identify and prioritize target investors | Targeting plan | Anchor/cornerstone investors identified |
| 4 | Draft prospectus | Company, legal, auditors | Due diligence (business/legal/financial) and drafting | Preliminary prospectus (red herring) | KPI consistency, auditor comfort letter |
| 5 | Regulatory review | Regulator, company, counsel | Comment letters ↔ responses until clearance | Approval / Effective | Review timelines, sensitive issues |
| 6 | Valuation & price range | Underwriters, company | Peers, DCF/comps, set indicative range | Valuation memo, price range | Track comps and market conditions |
| 7 | Roadshow | Management, underwriters | Teach-ins, 1:1s, group meetings | Investor feedback | Segment-specific messaging, tough Q&A |
| 8 | Book building | Underwriters | Collect orders (size/price); assess book quality | Order book | Mix of long-only vs. hot money |
| 9a | Firm commitment | Underwriters | Banks buy the issue then resell | Underwriting agreement | Market risk borne by syndicate |
| 9b | Best efforts | Underwriters | Placement without bank purchase | Placement agreement | Demand shortfall risk on issuer |
| 10 | Pricing & allocation | Underwriters, company | Set final price; allocate to investors | Pricing press release, final prospectus | Allocation discipline for post-IPO stability |
| 11 | Listing / first day | Exchange, market makers | First print; trading begins | Ticker live | Opening volatility |
| 12 | Stabilization / greenshoe | Underwriters | Over-allotment ~15% to smooth price | Stabilization report | Jurisdictional constraints |
| 13 | Settlement T+2 | CCP, custodians, brokers | Cash ↔ shares in two business days | Final settlement | Settlement fails, fail coverage |
| 14 | Post-IPO | Company, IR | Lock-ups 90–180 days; periodic reporting | 10-Q/10-K or local reports | IR calendar, guidance, blackout windows |

