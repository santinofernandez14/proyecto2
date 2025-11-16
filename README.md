flowchart TD

    A[Inicio] --> B[Mostrar menú]
    B --> C[Leer opción ingresada]

    %% --- OPCIÓN 1 --- %%
    C --> D{op == "1"?}
    D -->|Sí| D1[cargar_imagen()] --> B
    D -->|No| E{op == "2"?}

    %% --- OPCIÓN 2 --- %%
    E -->|Sí| E1[verificar_imagen_cargada()]
    E1 -->|Excepción| E2[Mostrar error: "Debe ejecutar primero la FUNCIÓN 1"] --> B
    E1 -->|OK| E3[Pedir keyword (youtube / instagram / twitter / facebook)]
    E3 --> E4[redimensionar_imagen(ruta_imagen_cargada, keyword)] --> B
    E -->|No| F{op == "3"?}

    %% --- OPCIÓN 3 --- %%
    F -->|Sí| F1[verificar_imagen_cargada()]
    F1 -->|Excepción| F2[Mostrar error] --> B
    F1 -->|OK| F3[ajustar_contraste(ruta_imagen_cargada)] --> B
    F -->|No| G{op == "4"?}

    %% --- OPCIÓN 4 --- %%
    G -->|Sí| G1[verificar_imagen_cargada()]
    G1 -->|Excepción| G2[Mostrar error] --> B
    G1 -->|OK| G3[Pedir nombre del filtro]
    G3 --> G4[aplicar_filtros(ruta_imagen_cargada, filtro)] --> B
    G -->|No| H{op == "5"?}

    %% --- OPCIÓN 5 --- %%
    H -->|Sí| H1[verificar_imagen_cargada()]
    H1 -->|Excepción| H2[Mostrar error] --> B
    H1 -->|OK| H3[Preguntar: "¿La imagen contiene una persona? (s/n)"]
    H3 --> H4[persona = (resp == "s")]
    H4 --> H5[boceto_persona(ruta_imagen_cargada, persona, invertir=True)] --> B
    H -->|No| I{op == "6"?}

    %% --- OPCIÓN 6 --- %%
    I -->|Sí| I1[Mostrar "Saliendo del programa..."] --> J[Fin]
    I -->|No| K[Mostrar "Opción inválida"] --> B


