# Errores encontrados en la versión del compañero

Mi suite (MP-1 a MP-4) atrapó sola **3** de los 5 errores: `segunElNumeroDeRetiro`, `retirarExactamenteElLimite` y `sinSaldoSuficiente, ninguna de las dos cuentas cambia`.

| Queja | Prueba que la reproduce                 | Qué estaba mal en el código (la línea y por qué)                                                                                                                              | ¿Mi suite ya lo atrapaba? |
| ----- | --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| 1     | `tercerRetiroGratis`                    | La lógica de la comisión cobraba `$10.00` en el tercer retiro, cuando los primeros tres retiros deben ser gratuitos.                                                          | sí                        |
| 2     | `retiroExactoDelLimite`                 | `CuentaBancaria.java:47` rechazaba un retiro de exactamente `$5000.00`, aunque el límite de `$5000.00` debe permitirse.                                                       | sí                        |
| 3     | `transferenciaRechazadaNoCambiaElSaldo` | La transferencia modificaba el saldo de la cuenta origen antes de comprobar que había saldo suficiente. Al rechazarse la operación, el saldo debía permanecer en `$10000.00`. | sí                        |
| 4     | `laComisionApareceEnElHistorial`        | La comisión de `$10.00` se descontaba del saldo, pero no se registraba un movimiento de tipo `COMISION` en el historial.                                                      | no                        |
| 5     | `elHistorialNoSePuedeModificar`         | `getMovimientos()` permitía modificar directamente la colección interna de movimientos, por lo que desde fuera se podían borrar movimientos con `clear()`.                    | no                        |
