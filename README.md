<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Diagrama de Flujo - Menú</title>

<!-- Cargar Mermaid desde CDN -->
<script src="https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.min.js"></script>

<script>
    mermaid.initialize({ startOnLoad: true });
</script>

<style>
    body{
        font-family: Arial, sans-serif;
        margin: 20px;
    }
</style>
</head>

<body>

<h2>Diagrama de Flujo del Menú</h2>

<div class="mermaid">
flowchart TD
    A[Inicio] --> B[Mostrar menú:<br/>1-Cargar imagen<br/>2-Redimensionar<br/>3-Ajustar contraste<br/>4-Aplicar filtros<br/>5-Boceto persona<br/>6-Salir]
    B --> C[Leer opción op]

    C --> D1{op == 1?}
    C --> D2{op == 2?}
    C --> D3{op == 3?}
    C --> D4{op == 4?}
    C --> D5{op == 5?}
    C --> D6{op == 6?}

    D1 -->|Sí| E1[cargar_imagen<br/>Guardar ruta_imagen_cargada] --> B
    D1 -->|No| C

    D2 -->|Sí| E2[verificar_imagen_cargada]
    E2 -->|Error| E2A[Mostrar: Debe ejecutar primero opción 1] --> B
    E2 -->|OK| E2B[Pedir keyword:<br/>youtube/instagram/twitter/facebook] --> E2C[redimensionar_imagen] --> B
    D2 -->|No| C

    D3 -->|Sí| E3[verificar_imagen_cargada]
    E3 -->|Error| E3A[Mostrar error] --> B
    E3 -->|OK| E3B[ajustar_contraste] --> B
    D3 -->|No| C

    D4 -->|Sí| E4[verificar_imagen_cargada]
    E4 -->|Error| E4A[Mostrar error] --> B
    E4 -->|OK| E4B[Pedir nombre del filtro] --> E4C[aplicar_filtros] --> B
    D4 -->|No| C

    D5 -->|Sí| E5[verificar_imagen_cargada]
    E5 -->|Error| E5A[Mostrar error] --> B
    E5 -->|OK| E5B[Preguntar: ¿Contiene persona? s/n] --> E5C[persona = resp==s] --> E5D[boceto_persona] --> B
    D5 -->|No| C

    D6 -->|Sí| E6[Mostrar: Saliendo del programa...] --> Z[Fin]
    D6 -->|No| E7[Mostrar: Opción inválida] --> B
</div>

</body>
</html>


