# Consignes de l'autopilote — FinancerMaFormation

Tu es lancé automatiquement chaque jour pour faire grossir le site, tout seul.
Dossier de travail : `/Users/antoninlopinto/BrainA/financer-ma-formation`

Le site oriente les pros (artisans, commerçants, libéraux, salariés…) vers le bon fonds de financement
de formation (FAFCEA, AGEFICE, FIF-PL, OPCO, CPF, VIVEA) et estime leur reste à charge.

## Ta mission (une seule page par exécution)

1. `git pull --rebase` (au cas où).
2. Ouvre `_autopilot/queue.md`, prends le PREMIER item non coché.
3. **Vérité des chiffres = non négociable.** Avant d'écrire un montant/plafond/taux, vérifie-le sur une source officielle de l'année en cours (service-public, URSSAF, site du fonds). En cas de doute, donne une fourchette + un lien vers la source, ne JAMAIS inventer un chiffre précis.
4. Construis la page en copiant la structure d'une page existante (`agefice-commercant.html` est le modèle) :
   - même `<nav>`, même `<footer>`, lien `styles.css`
   - `<title>` + `<meta description>` avec le mot-clé principal de l'item
   - intro claire, section "Comment ça marche / combien", section FAQ (2-3 questions)
   - un lien visible vers le simulateur de la page d'accueil (`index.html`)
   - une `note` d'avertissement "estimation à valeur indicative"
5. Ajoute une carte vers la nouvelle page dans la grille `.grid` de `index.html`.
6. Coche l'item dans `_autopilot/queue.md`.
7. Publie :
   ```
   git add -A && git commit -m "Autopilote : ajout de la page [nom]" && git push
   ```

## Standard de qualité (depuis le 01/06/2026)

Le site a été approfondi. Toute NOUVELLE page doit respecter ce standard (modèle : `comparatif-fonds-formation.html` ou `agefice-commercant.html`) :
- `<nav>` à 4 liens : Comparatif · Démarches · Mon OPCO · CPF 2026.
- Une ligne « Mis à jour le [date] » sous le chapô.
- Quand c'est pertinent : une section « Comment faire la demande ? » (où déposer, documents, délai, remboursement) et un rappel **Qualiopi obligatoire en 2026**.
- **Maillage interne** : lier au moins 2 pages connexes (comparatif, démarches, ou les guides par statut).
- Pied de page « de confiance » avec liens À propos · Sources · Mentions légales + mention « Information indépendante, non affiliée ».
- Si la page a une FAQ, ajouter un bloc `<script type="application/ld+json">` de type FAQPage.
- Penser à ajouter la nouvelle URL dans `sitemap.xml`.

## Règles de sécurité

- **Que de l'AJOUT.** Ne casse/supprime jamais une page existante (surtout pas le simulateur de `index.html`).
- **Une seule page par jour.**
- Si la file est vide : ajoute 3-4 idées de pages pertinentes (questions précises peu couvertes) en bas de `queue.md`, puis arrête-toi sans rien construire.
- Si `git push` échoue : `git pull --rebase` puis réessaie (max 3 fois). Jamais de push forcé.
- Travaille en autonomie, sans validation humaine (page additive).

## Monétisation (plus tard, ne pas faire maintenant)

Quand le site aura du trafic : bouton "Recevoir 3 devis de formation" (lead vers centres de formation, 20-80 €/lead),
programme d'apporteur d'affaires (≈10 % du montant facturé), affiliation logiciels (Digiforma). On construit l'audience d'abord.
