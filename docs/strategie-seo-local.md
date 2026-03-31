# Stratégie SEO local — siteartisan.fr
**Document de référence — à conserver**
Date de création : 2026-03-22

---

## 1. Informations du projet

| Champ | Valeur |
|---|---|
| Domaine | siteartisan.fr |
| Firebase project | sitespourartisans-e1949 |
| Hosting URL | https://sitespourartisans-e1949.web.app |
| Contact WhatsApp | +212 699 245 542 |
| N° Auto-Entrepreneur | 003405900000095 |
| Marché cible | France + Maroc + pays francophones |
| Métiers cibles | Coiffeurs, Salons de beauté, Blanchisseries, Boulangeries, Cours particuliers |

---

## 2. Architecture des URLs (silos SEO)

```
siteartisan.fr/
├── index.html                          ← Page d'accueil principale (leads)
├── boulangerie/index.html              ← Démo boulangerie
├── coiffeur/index.html                 ← Démo coiffeur
├── cours/index.html                    ← Démo cours particuliers
│
├── maroc/
│   ├── index.html                      ← Silo Maroc (À CRÉER)
│   ├── meknes/index.html               ✅ CRÉÉE — 2026-03-22
│   ├── casablanca/index.html           ← À créer
│   ├── marrakech/index.html            ← À créer
│   ├── fes/index.html                  ← À créer
│   ├── rabat/index.html                ← À créer
│   ├── tanger/index.html               ← À créer
│   ├── agadir/index.html               ← À créer
│   └── oujda/index.html                ← À créer
│
└── france/
    ├── index.html                       ← Silo France (À CRÉER)
    ├── gironde-33/
    │   ├── index.html                   ← Silo département (À CRÉER)
    │   ├── bordeaux/index.html          ← À créer
    │   ├── merignac/index.html          ← À créer
    │   └── pessac/index.html            ← À créer
    ├── paris-75/
    │   └── bordeaux/index.html          ← À créer
    ├── haute-garonne-31/
    │   └── toulouse/index.html          ← À créer
    └── ... (voir Phase 3 ci-dessous)
```

---

## 3. Pages déjà en ligne

| URL | Statut | Date |
|---|---|---|
| `/` | ✅ En ligne | — |
| `/boulangerie/` | ✅ En ligne | — |
| `/coiffeur/` | ✅ En ligne | — |
| `/cours/` | ✅ En ligne | — |
| `/maroc/meknes/` | ✅ En ligne | 2026-03-22 |

---

## 4. Règles SEO à respecter pour chaque nouvelle page

### Balises obligatoires
```html
<title>[Métier] à [Ville] ([Pays/Dept]) — siteartisan.fr</title>
<!-- Max 70 caractères -->

<meta name="description" content="[CTA local — max 160 caractères]" />
<link rel="canonical" href="https://siteartisan.fr/[chemin-complet]/" />
```

### Schema.org obligatoire
- `ProfessionalService` avec `areaServed` = ville cible
- `BreadcrumbList` pour le fil d'Ariane

### Maillage interne — règle des 3 liens
Chaque page ville doit avoir :
1. **Lien MONTANT** → vers le silo parent (pays / département)
2. **Lien LATÉRAL** → vers 2–3 villes du même niveau
3. **Lien RACINE** → vers l'accueil `/`

---

## 5. Plan de déploiement par phases

### Phase 1 — Pages racines (priorité haute)
- [ ] `/maroc/` — page silo Maroc
- [ ] `/france/` — page silo France
- [ ] `/artisans-france-maroc/` — page passerelle

### Phase 2 — Villes Maroc (8 villes)
- [x] `/maroc/meknes/` ✅ fait
- [ ] `/maroc/casablanca/`
- [ ] `/maroc/marrakech/`
- [ ] `/maroc/fes/`
- [ ] `/maroc/rabat/`
- [ ] `/maroc/tanger/`
- [ ] `/maroc/agadir/`
- [ ] `/maroc/oujda/`

### Phase 3 — Départements France (10 prioritaires)
- [ ] `/france/gironde-33/bordeaux/`
- [ ] `/france/paris-75/`
- [ ] `/france/haute-garonne-31/toulouse/`
- [ ] `/france/bouches-du-rhone-13/marseille/`
- [ ] `/france/rhone-69/lyon/`
- [ ] `/france/nord-59/lille/`
- [ ] `/france/alpes-maritimes-06/nice/`
- [ ] `/france/herault-34/montpellier/`
- [ ] `/france/bas-rhin-67/strasbourg/`
- [ ] `/france/loire-atlantique-44/nantes/`

### Phase 4 — Croisement métier × ville (objectif 80-100 pages)
Format : `/maroc/[ville]/[metier]/` et `/france/[dept]/[ville]/[metier]/`
Exemple : `/maroc/casablanca/coiffeur/`

---

## 6. Variations lexicales anti-duplication

| Générique | Variante A | Variante B |
|---|---|---|
| Site vitrine | Site web professionnel | Vitrine numérique |
| Artisan | Professionnel indépendant | Commerçant local |
| Devis gratuit | Estimation offerte | Sans engagement |
| Rendez-vous | Prise de contact | Réservation directe |
| En 3 jours | Livraison rapide | Sous 72h |
| Référencement local | Visibilité Google | Positionnement local |

---

## 7. Mots-clés cibles par marché

### Maroc
```
création site vitrine [ville]
site web artisan [ville]
site professionnel coiffeur [ville]
salon beauté [ville] site internet
blanchisserie [ville] site web
site artisan Maroc pas cher
```

### France
```
création site vitrine artisan [ville]
site vitrine coiffeur [département]
site web boulangerie [ville]
artisan [ville] devis site internet
site vitrine salon de beauté [code postal]
```

---

## 8. Template HTML — page ville locale

Copier ce template pour chaque nouvelle page ville :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <title>[Métier] à [Ville] — siteartisan.fr</title>
  <meta name="description" content="[160 car max]" />
  <link rel="canonical" href="https://siteartisan.fr/[chemin]/" />

  <!-- Schema LocalBusiness -->
  <script type="application/ld+json">
  {
    "@context":"https://schema.org",
    "@type":"ProfessionalService",
    "name":"siteartisan.fr",
    "areaServed":{"@type":"City","name":"[Ville]"},
    "telephone":"+212699245542"
  }
  </script>
</head>
<body>
  <!-- Breadcrumb -->
  <!-- H1 : Créez votre site vitrine d'artisan à [Ville] -->
  <!-- Contenu 200-300 mots localisé -->
  <!-- Section quartiers / zones -->
  <!-- Maillage villes voisines -->
  <!-- CTA WhatsApp -->
  <!-- Footer avec liens internes -->
</body>
</html>
```

---

## 9. Checklist avant mise en ligne d'une page

- [ ] Meta title ≤ 70 caractères
- [ ] Meta description ≤ 160 caractères
- [ ] Balise `canonical` correcte
- [ ] H1 contient le nom de la ville
- [ ] Schema.org `ProfessionalService` présent
- [ ] Schema.org `BreadcrumbList` présent
- [ ] Contenu ≥ 200 mots, localisé (quartiers, adresse réelle)
- [ ] 3 liens internes (montant + latéral + racine)
- [ ] Bouton WhatsApp avec message pré-rempli mentionnant la ville
- [ ] `firebase deploy --only hosting` exécuté
- [ ] URL vérifiée sur https://sitespourartisans-e1949.web.app

---

## 10. Commande de déploiement

```bash
cd "D:/site prospet local"
firebase deploy --only hosting
```

---

*Document généré par Claude — siteartisan.fr — 2026-03-22*
