# Validation du moteur de jeu de dames international

Le moteur Web est un port JavaScript de la logique exposée dans `JeanFrankRulesEngine.kt` et `DraughtsModels.kt`.

## Correspondances déjà vérifiées

| Règle / fonction | Référence Kotlin | Test Web |
|---|---|---|
| Numérotation 1–50 | `toRowCol`, `toSquare` | Bijection des 50 cases |
| Départ standard | `initialPosition` | 20 pièces par camp, 9 coups blancs |
| Prise des pions dans les deux sens | `findManCaptures` | Capture arrière 28x37 |
| Prise obligatoire | `getLegalMoves` | Les coups simples sont écartés |
| Prise majoritaire | `getLegalMoves` | Rafle de 2 pièces préférée |
| Promotion en fin de rafle | `isPromotionSquare`, `applyMove` | Promotion différée testée |
| Dame volante | `findKingCaptures` | Plusieurs cases d'atterrissage testées |
| Pièce capturée laissée sur le damier durant la rafle | `capturedSet` | Test Turkish strike |
| Répétition triple | `positionSignature`, `positionKeys` | Cycle de répétition testée |
| 25 coups de dame sans prise | `kingOnlyMoves` | Seuil de réclamation testé |
| Abandon / accord de nulle | `resign`, `acceptDraw` | Résultat final testé |

## Limites connues

- La parité exhaustive Kotlin/Web sur un grand corpus de positions n'a pas encore été exécutée.
- Les règles particulières de nullité au-delà des deux critères repris de la source Kotlin doivent être confirmées sur le règlement FMJD en vigueur avant de présenter le moteur comme homologué.
- Le moteur de recherche IA Kotlin (`JeanFrankSearchEngine.kt`) n'est pas encore porté.
- Les tests couvrent les positions écrites dans les fichiers de tests et les 10 chemins d'exercices du projet ; ils ne prouvent pas à eux seuls l'absence de tout défaut.
