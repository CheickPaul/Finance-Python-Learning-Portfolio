# Lesson – Buying, Selling, and Settlement

## Key Concepts
* Dojima (Japon, XVIIIᵉ) : premiers échanges à terme, « pit trading » et règles de séance.
* Mark-to-market quotidien : variation margin créditée/débitée sur le compte de marge.
* Livraison physique : si la position n’est pas close avant l’échéance, le long reçoit et le short livre.
* Règlement en espèces (cash-settled) : pour des sous-jacents non livrables (indices, immobilier).
* Arbitrage & convergence : à l’échéance, le future converge vers le spot.

---

## My Notes
* **Maïs** : producteur short futures pour fixer son prix, industriel long pour sécuriser son coût.
* **Pétrole (WTI)** : livraison physique à Cushing, Oklahoma ; sortie avant FND pour les financiers.
* **Ultra Bond (UB30)** : panier d’OAT/UST ≥ 25 ans ; choix du **Cheapest-to-Deliver (CTD)** et **conversion factor (CF)**.
* **S&P 500 futures** : cash-settled ; outil standard de couverture et de spéculation sans risque de livraison.
* **Housing futures** : uniquement cash-settled (on ne « livre » pas des maisons).

---

## Reflection

### 1) Mark-to-Market, Variation Margin et Appels de Marge

Soit un future de prix de clôture (settlement) \(F_t\) au jour \(t\), un prix de veille \(F_{t-1}\), un **multiplier** \(M\) et un nombre de contrats \(N\).

**P&L quotidien (long)** :
\[
\Delta \Pi_t^{\text{long}} = N \, M \, (F_t - F_{t-1})
\]
**P&L quotidien (short)** :
\[
\Delta \Pi_t^{\text{short}} = -\,N \, M \, (F_t - F_{t-1})
\]

Le compte de marge est crédité/débité chaque jour de \(\Delta \Pi_t\).  
Si le solde < **maintenance margin**, appel de marge pour revenir au **initial margin**.

> Remarque : le **settlement price** \(F_t\) n’est pas forcément le dernier trade (évite les manipulations) ; il est fixé par un comité.

---

### 2) Basis, Coût de Portage et Convergence

On note le **basis** :
\[
\text{Basis}_t = F_t - S_t
\]
où \(S_t\) est le prix spot. Sous hypothèses de **coût de portage** (taux \(r\), stockage \(c\), convenience yield \(y\)), la relation théorique (continuous compounding) est :
\[
F_t = S_t \, e^{(r + c - y)T}
\]

À l’échéance \(T \to 0\) :
\[
\lim_{T \to 0} (F_T - S_T) = 0
\]
donc
\[
F_T \to S_T
\]
La convergence est renforcée par l’arbitrage (cash-and-carry / reverse cash-and-carry) lorsque le basis s’écarte de la valeur justifiée par \((r,c,y)\).

**Cash-and-Carry (si \(F_t\) trop élevé)** :
* Acheter spot, financer au taux \(r\), stocker (\(c\)), **vendre** le future.
* Profit à l’échéance par convergence de \(S_T\) et \(F_T\).

**Reverse Cash-and-Carry (si \(F_t\) trop bas)** :
* **Vendre** le spot (ou emprunter le sous-jacent), placer au taux \(r\), **acheter** le future.

---

### 3) Futures à Livraison Physique : Facturation et CTD (obligataires)

Pour un future obligataire (ex. **UB30**), le short livre une obligation du panier éligible.  
La facture payée au short (hors frais) est :
\[
\text{Invoice Price} = F_{\text{final}} \times CF \times M + AI
\]
où :
* \(F_{\text{final}}\) = prix du future au règlement,
* \(CF\) = **conversion factor** de l’obligation livrée,
* \(M\) = **multiplier** du contrat,
* \(AI\) = **accrued interest** (intérêt couru) sur l’obligation livrée.

**Choix du CTD** : le vendeur rationnel livre le titre qui maximise son profit, i.e. celui qui **minimise** son coût effectif de livraison. Deux métriques utiles :
* **Net Basis** (approche prix) :
  \[
  \text{NetBasis} = P_{\text{obligation}} - (F \cdot CF) - AI
  \]
  Le CTD tend à minimiser \(\text{NetBasis}\).
* **Implied Repo Rate (IRR)** (approche rendement) :
  \[
  IRR = \frac{ \big( \text{Coupons} + P_{\text{obligation}} - (F \cdot CF) \big) }{ (F \cdot CF) } \times \frac{360}{\text{jours}}
  \]
  Le CTD tend à **maximiser** l’\(IRR\) par rapport au repo de marché.

---

### 4) Cash-Settled Futures : Payoff et Lecture des Prix

Pour un future **cash-settled** (ex. **S&P 500**), il n’y a pas de livraison de l’indice.  
Le règlement final (au dernier jour) crédite/débite :
\[
\text{Cash Settlement} = N \, M \, (I_{\text{final}} - F_{\text{final}})
\]
où \(I_{\text{final}}\) est le niveau d’indice de référence au fixing final, \(F_{\text{final}}\) le prix de règlement du future.  
Dans la pratique, tout cela résulte de la **somme des mark-to-market quotidiens**, déjà matérialisés via \(\Delta \Pi_t\).

---

### 5) Arbitrage de Date et Convergence à l’Échéance

À l’approche de l’échéance \(T\), l’écart **basis** se ferme mécaniquement :
\[
\text{Basis}_t = F_t - S_t \xrightarrow[t \to T]{} 0
\]
Si \(\text{Basis}_t\) est anormal (trop positif ou trop négatif) compte tenu de \((r,c,y)\), les stratégies **cash-and-carry** ou **reverse** deviennent rentables et forcent le réalignement.

---

### 6) Synthèse Opérationnelle
* **Mark-to-market** : \(\Delta \Pi_t = N M (F_t - F_{t-1})\), alimente la marge et déclenche les appels de marge.
* **Convergence** : \(F_T \to S_T\) ; le **basis** tend vers 0 à l’échéance.
* **Livraison physique** : attention aux dates FND/LTD ; sur UB30, la facture dépend de \(CF\) et \(AI\), choix du **CTD** par max \(IRR\)/min NetBasis.
* **Cash-settled** : pas de logistique ; le règlement final est purement monétaire et équivaut à la somme des variations quotidiennes.

