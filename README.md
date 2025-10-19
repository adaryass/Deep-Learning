Intoduction: 

Definition 

- Le percepton: est l'unité de base de réseaux de neurones. Il s'agit d'un modèle de classification binaire, capable de séparer linéairement 2 classes de poids.

  <img width="1536" height="1024" alt="ChatGPT Image 19 oct  2025, 19_42_18" src="https://github.com/user-attachments/assets/a4a3f3e8-db42-48c4-b781-488752b22721" />





```mermaid
flowchart TB
    %% === Style des blocs ===
    classDef main fill:#111,color:#fff,stroke:#888,stroke-width:2px
    classDef sub fill:#1a1a1a,color:#fff,stroke:#555
    classDef math fill:#000,color:#0f0,font-size:12px,stroke:#333

    %% === Entrée ===
    XY((X, y)):::math

    %% === Étapes principales ===
    Init[Initialisation(X)]:::main
    Model[Model(X, W, b)]:::main
    Cost[Cost(A, y)]:::main
    Grad[Gradients(A, X, y)]:::main
    Update[Update(W, b, dW, db)]:::main

    %% === Formules à droite ===
    Zmath["Z = X · W + b<br/>A = 1 / (1 + e^{-Z})"]:::math
    Costmath["L = -1/m Σ [ y log(A) + (1 - y) log(1 - A) ]"]:::math
    Gradmath["∂L/∂W = (1/m) Xᵀ (A - y)<br/>∂L/∂b = (1/m) Σ(A - y)"]:::math
    Upmath["W = W - α ∂L/∂W<br/>b = b - α ∂L/∂b"]:::math

    %% === Liens ===
    XY --> Init
    Init --> Model
    Model --> Cost
    Cost --> Grad
    Grad --> Update
    Update --> Model

    %% === Liens vers formules ===
    Model -- Calcul --> Zmath
    Cost -- Fonction de perte --> Costmath
    Grad -- Dérivées --> Gradmath
    Update -- Mise à jour --> Upmath

<img width="1024" height="1536" alt="ChatGPT Image 19 oct  2025, 19_57_05" src="https://github.com/user-attachments/assets/f928e945-18da-4278-badf-e360920a3d8e" />
