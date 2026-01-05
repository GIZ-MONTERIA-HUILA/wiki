[Inicio](/README.md)

# Casos de prueba

## Descripción

Los casos de prueba validan el correcto funcionamiento de los módulos del SNIF conforme a las historias de usuario y requerimientos.

## Estructura de los casos

| ID    | Caso de prueba             | Objetivo                                 | Resultado esperado               | Estado |
| ----- | -------------------------- | ---------------------------------------- | -------------------------------- | ------ |
| CP-01 | Verificar descarga GeoJSON | Validar formato y atributos              | Archivo descargado correctamente | Éxito  |
| CP-02 | Validar autenticación AD   | Confirmar login contra directorio activo | Sesión establecida               | Éxito  |

## Estrategia de prueba

- Pruebas unitarias en backend.
- Pruebas de integración con servicios GIS.
- Validación en ambiente de staging.

## Resultados

Los resultados se documentan en formato `.csv` y `.pdf` dentro del directorio `/tests/results`.
