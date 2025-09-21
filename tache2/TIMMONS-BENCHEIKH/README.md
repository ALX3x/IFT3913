# Binôme

- Wayne Timmons  
- Ayoub Bencheikh  

# Tâche 2 — Tests de SpeedWeighting

## Classe testée
- `com.graphhopper.routing.weighting.SpeedWeighting`

## Nouveaux cas de test ajoutés (7)

### 1. testCalcEdgeWeightNormal
- **Intention :** Vérifier que `calcEdgeWeight()` retourne bien `distance / speed` quand la vitesse est > 0.  
- **Données de test :** distance = 1000.0, vitesse = 50.0.  
- **Oracle attendu :** Résultat = 20.0 (1000 / 50).  

### 2. testCalcEdgeWeightZeroSpeed
- **Intention :** Vérifier que `calcEdgeWeight()` retourne `Double.POSITIVE_INFINITY` si la vitesse est 0.  
- **Données de test :** vitesse = 0.0.  
- **Oracle attendu :** Résultat = `Double.POSITIVE_INFINITY`.  

### 3. testCalcEdgeWeightReverse
- **Intention :** Vérifier que `calcEdgeWeight()` utilise `getReverse(speedEnc)` quand `reverse = true`.  
- **Données de test :** distance = 500.0, vitesse inverse = 25.0.  
- **Oracle attendu :** Résultat = 20.0 (500 / 25).  

### 4. testCalcEdgeMillis
- **Intention :** Vérifier que `calcEdgeMillis()` retourne le poids en millisecondes (`calcEdgeWeight * 1000`).  
- **Données de test :** distance = 100.0, vitesse = 10.0.  
- **Oracle attendu :** Résultat = 10000 ms ((100 / 10) * 1000).  

### 5. testCalcMinWeightPerDistance
- **Intention :** Vérifier que `calcMinWeightPerDistance()` retourne `1 / maxSpeed`.  
- **Données de test :** maxSpeed = 120.0.  
- **Oracle attendu :** Résultat = 1/120.  

### 6. testGetName
- **Intention :** Vérifier que `getName()` retourne la chaîne `"speed"`.  
- **Données de test :** aucune donnée spécifique.  
- **Oracle attendu :** `"speed"`.  

### 7. testHasTurnCosts
- **Intention :** Vérifier que `hasTurnCosts()` retourne `true` si un `TurnCostProvider` est configuré.  
- **Données de test :** `TurnCostStorage` non nul, `uTurnCosts = 5.0`.  
- **Oracle attendu :** `true`.  
