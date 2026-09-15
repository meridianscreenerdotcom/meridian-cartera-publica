# Correcciones al libro mayor

## 15/09/2026 — capital inicial 10.300,03 € y retirada de la aportación de 200 € del 07/09

- El simulador de IBKR no admite ingresos periódicos: la aportación de 200 € registrada el 07/09/2026 nunca entró en
  la cuenta paper. Se retira del libro. Desde aquí la cartera opera solo con el capital inicial, sin aportaciones.
- La cuenta paper se sembró con 10.300,03 € (300,03 € más de los 10.000 € registrados; diferencia constante medida
  el 04 y el 05/09/2026). Se registra como capital inicial con fecha 20/08/2026.
- Efecto: efectivo 26,37 → 126,40 € (igual al saldo del simulador); aportado 10.200 → 10.300,03 €; valoraciones del
  histórico +300,03 € antes del 07/09 y +100,03 € desde entonces (llevaban los 200 € fantasma).
- La huella SHA-256 de los movimientos cambia con este commit: 44ee45eae80a… → 0963b9b0898c…
