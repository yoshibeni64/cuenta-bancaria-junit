# Cuenta bancaria — pruebas unitarias con JUnit 5

**Autor:** José Rodrigo Benítez Rivera

## Cómo correr las pruebas

    ./probar.sh final

## Qué prueba cada clase

| Clase de prueba | Qué prueba | Cuántas pruebas |
|---|---|---:|
| DepositoTest | Depósitos y saldo inicial de una cuenta | 2 |
| RetiroTest | Retiros, límites, saldo insuficiente y validaciones | 8 |
| TransferenciaTest | Transferencias, validaciones y movimientos | 7 |
| InteresTest | Cálculo del interés mensual según el saldo | 7 |
| ComisionTest | Comisiones según el número de retiro | 6 |
| QuejasTest | Reproducción de las cinco quejas de clientes | 5 |
| CierreDeCuentaTest | Cierre de cuentas y operaciones sobre cuentas cerradas | 7 |

## Boleto de salida

1. ¿Por qué una prueba que nunca viste en rojo no es confiable? Da un ejemplo de hoy.

   Porque si nunca falla, no sabemos si realmente detecta el problema que queremos probar. Un ejemplo de hoy fue el ciclo 4, en la cual inicialmente la prueba falló porque el método depositar() permitía depositar en una cuenta cerrada; después de corregirlo, la prueba pasó.

2. ¿Qué error se escondía en un valor frontera, y qué prueba lo atrapó?

   El retiro de exactamente $5,000.00 era un valor frontera. La prueba retirarExactamenteElLimiteSePermite atrapó que ese valor estaba siendo rechazado aunque debía permitirse.

3. ¿Qué cambió en tu forma de programar al escribir la prueba ANTES del código (MP-6)?

   Aprendí a definir primero el comportamiento esperado mediante una prueba y después escribir el código mínimo para hacerla pasar. Esto permitió detectar errores de forma más clara y hacer cambios con mayor seguridad.
