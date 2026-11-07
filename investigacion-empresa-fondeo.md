# Investigación: empresas de fondeo (prop firms) para operar con bot

Fecha: 2026-11-07. Las reglas cambian seguido: confirma siempre en la web oficial de la empresa antes de pagar un challenge.

## Recomendación corta

| Si tu bot es... | Empresa recomendada | Por qué |
|---|---|---|
| EA de MetaTrader (forex/índices/oro) | **FTMO** (1ª opción) o **The5ers** | Las más establecidas, permiten EAs y publican reglas claras |
| Bot de cripto por API (Python, etc.) | **Propr.xyz** (verificar) | Reglamento sin restricciones a bots y API pública con SDK Python/JS |
| Bot que dispara órdenes desde alertas de TradingView | FTMO / The5ers vía puente a MT5 | Funciona si la ejecución final es tu propio EA |

## Forex / CFDs (MetaTrader)

### FTMO
- Permite EAs.
- **Prohibido:** generar más de **2,000 solicitudes al servidor por día** (abrir, modificar o cerrar órdenes); el servidor también limita a 200 órdenes abiertas a la vez. Si el bot causa "hiperactividad" te piden cambiar la lógica.
- Ojo con EAs comprados/de terceros: si muchos traders usan el mismo EA te pueden negar la cuenta por la regla de asignación máxima de capital.
- Fuentes: https://ftmo.com/en/forbidden-trading-practices/ y https://ftmo.com/en/faq/which-instruments-can-i-trade-and-what-strategies-am-i-allowed-to-use/

### The5ers
- Permite EAs **solo si tú eres dueño del código fuente** (nada de bots alquilados o "caja negra").
- **Prohibido:** HFT (operaciones de pocos segundos), tick scalping, arbitraje (de latencia, hedge, reverso), scalping en rollover, copiar señales externas, stop-loss oculto ("stealth"), órdenes pendientes a ambos lados en noticias de alto impacto, cambios bruscos de tamaño de posición.
- Si rompes estas reglas: cuenta cancelada y sin reembolso.
- Fuentes: https://www.the5ers.com/faqs/prohibited-trading-practices/ y https://the5ers.com/faqs/can-i-use-an-ea-expert-advisor-can-i-set-a-stealth-mode-stop-loss/

### Otras que también aparecen como "EA-friendly" (solo fuentes de reseñas, sin verificar en web oficial)
- FundedNext, E8 Markets, Alpha Capital Group, FundingPips (puede restringir bots 100% automáticos sin supervisión).

## Cripto (bots por API)
- **Propr.xyz:** reglamento sin restricciones a bots; API REST con SDK Python/JS (beta). Empresa nueva: revisar reputación y pagos.
- **Velotrade:** dice permitir bots y API en todas las cuentas (pero la información viene de su propio blog).
- **Crypto Fund Trader:** permite bots excepto HFT, tick scalping y arbitraje.
- **HyroTrader:** información contradictoria; sus términos prohíben bots "salvo que lo permitan las Trading Rules". Preguntar al soporte antes.
- **No permiten bots:** Bitfunded, Kraken Prop. SizeProp no permite bots por API directa.

## Lista de control antes de pagar el challenge
1. ¿El bot es tuyo (tienes el código)? Si no, descarta The5ers y ten cuidado con FTMO.
2. ¿Cuántas órdenes/modificaciones hace al día? Debe quedar muy por debajo de 2,000.
3. ¿Usa martingala, grid, HFT o arbitraje? Casi todas lo prohíben o lo limitan.
4. ¿Pone stop-loss visible en cada operación? Debe hacerlo.
5. ¿Respeta la pérdida diaria máxima y la pérdida total de la empresa? Programa esos límites dentro del bot.
6. Haz backtest y prueba el bot en la cuenta demo/gratis de la empresa antes de comprar.
7. Corre el bot en un VPS para que no se apague.

## Fuentes de reseñas consultadas (no oficiales, posibles afiliados)
- https://tradersunion.com/ratings/prop/common/with-ea/
- https://www.quantvps.com/blog/top-prop-firms-for-ea-traders
- https://roya-trading.com/blog/best-prop-firm-trading-bots-api/
- https://www.hyrotrader.com/blog/best-crypto-prop-trading-firms/
- https://velotrade.com/blog/best-crypto-prop-firms-algo-traders
- https://www.sizeprop.com/blog/best-crypto-trading-bots-prop-firms
