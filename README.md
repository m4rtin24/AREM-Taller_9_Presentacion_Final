# Taller 9 - Simulacion de Comite de Arquitectura

**Curso:** Arquitectura Empresarial - Universidad de La Sabana  
**Equipo:** Adictos al Azucar - Juan Pablo Luna Zuleta, Alejandro Riveros y Martin Ortega  
**Cliente:** Jefatura de Cultura de Innovacion y Servicio - Direccion de Desarrollo Estrategico  
**Proyecto:** Actualizacion del directorio de extensiones telefonicas

## Propuesta en una frase

Convertir el directorio de extensiones, hoy mantenido manualmente en Excel, en una fuente institucional gobernada dentro de Microsoft 365, con conciliacion mensual por excepciones y un ciclo trazable de solicitud y confirmacion con la Direccion de Tecnologia.

## Entrega

| Entregable | Archivo | Estado |
|---|---|---|
| Presentacion ejecutiva de 9 min 40 s | [`presentacion/Taller9_Comite_Arquitectura_Equipo3.pptx`](presentacion/Taller9_Comite_Arquitectura_Equipo3.pptx) | Completa |
| Guion cronometrado | [`presentacion/guion-presentacion.md`](presentacion/guion-presentacion.md) | Completo |
| Preguntas de defensa | [`presentacion/preguntas-defensa.md`](presentacion/preguntas-defensa.md) | Completo |
| Matriz de riesgos de 7 dominios | [`presentacion/matriz-riesgos.xlsx`](presentacion/matriz-riesgos.xlsx) | Completa, editable y con formulas |
| Resumen ejecutivo | [`entrega/resumen-ejecutivo.md`](entrega/resumen-ejecutivo.md) | Completo |
| Roadmap y gestion del cambio | [`entrega/plan-implementacion.md`](entrega/plan-implementacion.md) | Completo |
| Gobierno, principios, estandares y 3 metricas | [`entrega/plan-gobernanza.md`](entrega/plan-gobernanza.md) | Completo |
| Procedimiento de cambios y ADR reales | [`entrega/procedimiento-cambios.md`](entrega/procedimiento-cambios.md) | Completo; incluye 3 ADR |
| Vista ArchiMate de Motivacion | [`entrega/vistas-finales/archimate-motivacion.drawio`](entrega/vistas-finales/archimate-motivacion.drawio) y [`PNG`](entrega/vistas-finales/archimate-motivacion.png) | Editable y exportada |
| Vista ArchiMate de Migracion | [`entrega/vistas-finales/archimate-migracion.drawio`](entrega/vistas-finales/archimate-migracion.drawio) y [`PNG`](entrega/vistas-finales/archimate-migracion.png) | Editable y exportada |
| Formulario de retroalimentacion | [`entrega/retroalimentacion-cliente.md`](entrega/retroalimentacion-cliente.md) | Listo para diligenciar; sin firma inventada |
| Reflexion individual | [`entrega/reflexiones/borrador-reflexion-individual.md`](entrega/reflexiones/borrador-reflexion-individual.md) | Solo borrador para personalizar |
| Referencias | [`entrega/referencias.md`](entrega/referencias.md) | Completo |
| Matriz de trazabilidad y control de entrega | [`entrega/anexos/trazabilidad-entregables.md`](entrega/anexos/trazabilidad-entregables.md) | Completa |

## Hallazgo central

El problema visible son las llamadas mal transferidas. La causa arquitectonica esta en el mantenimiento del directorio: aproximadamente 6.400 registros se revisan para encontrar entre 5 y 10 novedades, la nomina llega con hasta 45 dias de desfase y la Direccion de Tecnologia no devuelve una confirmacion estructurada cuando aprovisiona o libera una extension.

La propuesta no automatiza decisiones ambiguas ni modifica el PBX. Separa cuatro responsabilidades:

1. Biblioteca institucional restringida para recibir y versionar la nomina.
2. Conciliacion automatizada que produce excepciones y conserva validacion humana.
3. Directorio gobernado en Microsoft Lists o SharePoint como fuente unica de consulta.
4. Solicitudes trazables con identidad, fechas, estados, respuesta y escalamiento.

## Decisiones que gobiernan la propuesta

- El directorio institucional en Lists reemplaza al Excel en OneDrive como fuente unica.
- La conciliacion objetivo se ejecuta con Power Automate y SharePoint mediante conectores estandar; Power Query queda como alternativa de contingencia o prototipo, no como arquitectura objetivo concurrente.
- Los cambios sensibles requieren validacion humana. La automatizacion no libera una extension ni cambia un titular por una coincidencia ambigua.
- El PBX permanece fuera del alcance. Tecnologia conserva la operacion tecnica y confirma el resultado mediante una solicitud autenticada.

Estas decisiones estan formalizadas como ADR en el procedimiento de cambios.

## Limites y validaciones abiertas

La entrega define una arquitectura objetivo academica. No afirma que exista un despliegue aprobado. Antes de un piloto con datos reales, la Universidad debe confirmar permisos del tenant, licencias efectivas, politicas DLP, base juridica, retencion, grupos de acceso, propietario y copropietario de los flujos, catalogos de unidades y cargos, y un plazo de respuesta con Tecnologia.

El repositorio no contiene nomina ni directorio reales. Los artefactos usan estructuras y datos sinteticos. La retroalimentacion del cliente queda sin diligenciar y sin firma hasta que la complete la persona autorizada.

## Fuentes de continuidad

La entrega consolida el material del proyecto en [`JhonlunKnox/AREM-Equipo3-Universidad-de-la-Sabana`](https://github.com/JhonlunKnox/AREM-Equipo3-Universidad-de-la-Sabana) y sigue la guia oficial del [`Taller 9`](https://github.com/CesarAVegaF312/AREM-Taller_9_Presentacion_Final). Este repositorio se trata como entrega independiente. No requiere merge ni pull request hacia el repositorio docente.

