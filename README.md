# Cartera virtual de MeridIAn Screener — libro mayor público

Registro **público y verificable** de la cartera virtual que gestiona el sistema de
[meridianscreener.com](https://meridianscreener.com): 10.000 € iniciales en el simulador de
Interactive Brokers, aportación mensual, selección por ranking cuantitativo y reglas fijas de
rotación. No hay dinero real detrás; lo que se audita aquí es que **las decisiones y los
resultados que muestra la web no se han reescrito a posteriori**.

## Qué hay en este repositorio

| Fichero | Contenido |
|---|---|
| `LIBRO_MAYOR.md` | Todos los movimientos (compras, ventas, aportaciones, dividendos) con fecha, precio, comisión y motivo, en formato legible. |
| `VALORACIONES.csv` | Valor de la cartera en cada revisión (semanal), aportado acumulado y rentabilidad. La curva del track record. |
| `cartera_demo.json` | El estado completo de la cartera tal cual lo usa el sistema (transparencia técnica). |

## Por qué esto es una prueba y no solo una tabla

Cada cambio se publica como un commit. **La fecha de cada commit la pone GitHub en sus
servidores**, no el autor: "en tal fecha la cartera era esta" queda atestiguado por un tercero.
Reescribir el historial (force-push) es técnicamente posible, pero cambia todos los hashes de
commit y lo detecta cualquiera que haya clonado el repositorio antes.

## Cómo verificar la huella

Al final de `LIBRO_MAYOR.md` y en el mensaje de cada commit figura la huella SHA-256 de la
lista de movimientos. Para recalcularla desde el JSON del mismo commit:

```bash
python3 -c "import json,hashlib; c=json.load(open('cartera_demo.json')); \
print(hashlib.sha256(json.dumps(c['movimientos'], sort_keys=True, ensure_ascii=True).encode()).hexdigest())"
```

Si coincide, ese JSON es exactamente el que produjo el libro mayor de ese commit. Si en un
commit posterior cambiara un movimiento antiguo, la huella dejaría de encadenar con la anterior.

## Aviso

Cartera de simulación con fines de investigación y divulgación. No es asesoramiento financiero
ni una recomendación de inversión. Más información y aviso legal en
[meridianscreener.com/privacidad/](https://meridianscreener.com/privacidad/).
