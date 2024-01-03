# Opis stanowiska

# Zadanie do wykonania

# Algorytm działania

<!-- ```mermaid -->
```{.mermaid caption="Test mermaid"}
%%{init:{'theme':'forest', 'flowchart': {'curve':'basis'}}}%%
flowchart TB
    app[Aplikacja mobilna]:::green

    subgraph vm[Maszyna wirtualna / sieć wewnętrzna]
        proxy[Moduł równoważenia obciążenia]:::green
        security[Serwis zapewniający bezpieczeństwo]:::green
        messaging(Kolejka komunikatów):::green
        gameplay[Serwis nadzorujący rozgrywkę]:::green
        users[(Baza danych użytkowników)]:::green
        plays[(Baza danych rozgrywek)]:::green
    end

    security <--> users
    gameplay <--> plays
    gameplay --> messaging <--> gameplay
    app <--HTTPS--> proxy
    proxy <--R2DBC--> security
    proxy <--> gameplay

    classDef green fill:#689F38,color:#FFF,stroke:#444
    style vm fill:#e3e3e3,color:#333333,stroke:#838383
```

![Test zdjęcia](./img/app_4_players.jpg)

