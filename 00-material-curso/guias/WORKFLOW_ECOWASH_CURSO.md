# Workflow EcoWash — Curso Software Asistido por IA

## 1. Propósito

Esta guía mantiene organizadas las reglas e instrucciones relacionadas con Jira, GitHub, Pull Requests, Code Reviews y el desarrollo del proyecto EcoWash dentro del curso Software Asistido por IA.

El documento distingue entre instrucciones comunicadas por el profesor y buenas prácticas de trabajo que adoptaremos como equipo para mantener un flujo ordenado, trazable y responsable.

## 2. Flujo general de trabajo

```text
Jira
→ análisis del ticket
→ Figma/diseño cuando aplique
→ revisión del código existente
→ branch
→ implementación
→ pruebas
→ validaciones
→ commit
→ push
→ Pull Request
→ reviewers
→ approvals
→ merge
```

## 3. Pull Requests

Instrucciones comunicadas por el profesor:

- El creador del PR debe agregarse como Assignee.
- Deben agregarse Reviewers.
- Entre los reviewers debe incluirse al profesor Bryan cuando corresponda al proceso de revisión indicado en clase.
- El dueño del PR debe solicitar activamente los reviews necesarios.
- No cerrar/mergear el PR mientras falten reviews requeridos.

## 4. Labels

Instrucciones registradas:

- Trabajo relacionado con agentes/maintenance -> label `maintenance`.
- Nuevas funcionalidades/features -> label `enhancement`.
- Cuando esté listo para revisión/QA -> registrar el estado/label `waiting for QA` según la configuración disponible en GitHub/Jira.

No se registran labels adicionales que no hayan sido confirmados.

## 5. Approvals y Merge

Regla comunicada en clase:

Antes del merge se requieren 3 approvals:

- profesor Bryan
- compañero/reviewer 1
- compañero/reviewer 2

No hacer merge mientras falten approvals requeridos.

## 6. Code Reviews

Instrucciones comunicadas por el profesor:

- Cada estudiante debe participar haciendo code reviews.
- No basta con crear PR propios.
- El profesor indicó que la rúbrica contempla penalizaciones relacionadas con no realizar el mínimo requerido de revisiones.
- El dueño del PR debe solicitar las revisiones.
- Los compañeros deben completar las revisiones para no bloquear el cierre del PR.

No se registra un número mínimo de reviews porque no está confirmado en el material disponible.

## 7. CODEOWNERS e invitaciones

Aspectos operativos a verificar:

- Verificar que los integrantes hayan aceptado las invitaciones al repositorio.
- Verificar CODEOWNERS cuando corresponda.
- Una invitación pendiente puede impedir que un compañero participe correctamente.
- La ausencia/configuración incorrecta de CODEOWNERS puede afectar la asignación automática de reviewers.

## 8. Jira y Figma

Instrucciones y referencias de trabajo:

- Los tickets actuales se administran en Jira.
- Los nuevos tickets UI deben revisarse contra Figma antes de implementar.
- El ticket debe ser la referencia funcional del trabajo.
- Figma sirve como referencia visual para UI.

## 9. Buenas prácticas adoptadas por nosotros

Esta sección describe nuestro workflow recomendado. No debe interpretarse como una regla comunicada por el profesor.

1. Leer ticket completo.
2. Revisar criterios de aceptación.
3. Revisar Figma cuando aplique.
4. Inspeccionar arquitectura/código existente antes de generar código.
5. Crear rama desde la base correcta.
6. Implementar cambios pequeños y trazables.
7. Ejecutar tests.
8. Ejecutar lint/format/build según corresponda.
9. Revisar manualmente el diff.
10. Validar que no existan cambios fuera de alcance.
11. Commit descriptivo asociado al ticket.
12. Push.
13. Crear PR.
14. Configurar Assignee, Reviewers y Labels.
15. Solicitar reviews.
16. Atender comentarios de revisión.
17. Obtener approvals requeridos.
18. Merge solamente cuando corresponda.

## 10. Uso responsable de IA

La IA y los agentes pueden ayudar a implementar, analizar, documentar y revisar cambios, pero el estudiante sigue siendo responsable de comprender técnicamente lo realizado.

Antes de aceptar código generado con IA, se debe revisar el cambio, validar que respete la arquitectura del proyecto, confirmar que el alcance sea correcto, ejecutar pruebas cuando corresponda y revisar manualmente el diff.

El objetivo no es aceptar código únicamente porque fue generado por un agente, sino usar la IA como apoyo para producir trabajo que el equipo pueda explicar, mantener y defender técnicamente.

## 11. Checklist rápido antes de cerrar un ticket

- [ ] Ticket revisado
- [ ] Acceptance criteria verificados
- [ ] Figma revisado si aplica
- [ ] Código existente inspeccionado
- [ ] Rama correcta
- [ ] Implementación terminada
- [ ] Tests PASS
- [ ] Lint/format/build verificados según aplique
- [ ] Diff revisado manualmente
- [ ] Commit asociado al ticket
- [ ] Push realizado
- [ ] PR creado
- [ ] Assignee configurado
- [ ] Reviewers solicitados
- [ ] Label correcto
- [ ] Code reviews atendidos
- [ ] 3 approvals obtenidos cuando corresponda
- [ ] Merge autorizado
