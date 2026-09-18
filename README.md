# CTIE QCM

Plateforme de révision inspirée de **jiujiu/inap-qcm**, dédiée à quatre matières :

- Marchés publics
- GDPR / RGPD
- Loi du CTIE
- TOGAF

## Fonctionnalités conservées

- connexion Supabase par lien magique ;
- sauvegarde locale et synchronisation cloud des résultats ;
- tableau de bord **Ma progression** ;
- page **Mes erreurs** avec la question, la réponse donnée, la bonne réponse et l'explication ;
- entraînement matière par matière avec correction immédiate.

## Fonctionnalités volontairement absentes pour le moment

- aucun test mélangeant les quatre matières ;
- aucun test de 80 questions ;
- aucun mode examen chronométré.

## Banques de questions

Les quatre fichiers JSON sont volontairement initialisés vides. Ils seront alimentés à partir des documents de référence fournis ultérieurement.

Format attendu :

```json
{
  "subject": "GDPR",
  "questions": [
    {
      "id": 1,
      "concept": "GDPR-001",
      "question": "Question…",
      "answers": ["A", "B", "C", "D"],
      "correct": 1,
      "explanation": "Explication sourcée…"
    }
  ]
}
```

## Supabase

La configuration Supabase reprend celle de `inap-qcm` et utilise la table `quiz_results`. Les nouvelles matières sont distinguées via le champ `scope`.

> Si les politiques RLS de la table `quiz_results` limitent les valeurs de `scope`, il faudra les adapter pour accepter `MARCHES`, `GDPR`, `LOI_CTIE` et `TOGAF`.
