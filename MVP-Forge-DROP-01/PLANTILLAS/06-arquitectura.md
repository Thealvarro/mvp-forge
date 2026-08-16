# Arquitectura

## Diagrama

```
[Usuario]
    |
    v
[Frontend] ----> [Backend / API]
                      |
                      v
                 [Base de datos]
```

## Las piezas

| Pieza | Qué hace |
|---|---|
| Frontend | Lo que el usuario ve y toca |
| Backend | La lógica y las validaciones |
| Base de datos | Donde queda guardada la información |

## Recorrido de una acción real

Toma la acción más importante del producto y sígela de punta a punta:

1. El usuario aprieta [botón]
2. El frontend envía [qué]
3. El backend valida [qué]
4. Se guarda en [dónde]
5. El usuario ve [qué]

## Decisiones

| Decisión | Por qué | Qué se descartó |
|---|---|---|
| | | |
