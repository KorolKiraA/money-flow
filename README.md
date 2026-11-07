# MoneyFlow

![Scala](https://img.shields.io/badge/Scala-3-red) ![License](https://img.shields.io/badge/license-MIT-blue) ![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)

A fintech-grade currency converter core with tiered fees and a multi-currency
wallet. All arithmetic runs on `BigDecimal` — no floating-point money bugs,
the same discipline real banking systems follow.

## Features

- Cross-rate conversion between 6 currencies (RUB, USD, EUR, CNY, KZT, AED)
- Progressive fee tiers: 3% → 1% depending on transaction size
- Multi-currency wallet with portfolio valuation in the base currency
- Effective post-fee rate shown for every conversion
- Exact `BigDecimal` math with banker's rounding

## Quick start

Requires **Scala 3** via [scala-cli](https://scala-cli.virtuslab.org/):

```bash
scala-cli run MoneyFlow.scala
```

## Sample output

```
1000 USD = 88128.38 EUR-equiv… 
1000.00 USD = 912.83 EUR  (fee 1850.00 RUB, effective rate 0.9128)

--- Multi-currency portfolio ---
       500.00 USD  =   46250.00 RUB
     20000.00 RUB  =   20000.00 RUB
  TOTAL: 66250.00 RUB
```

> Exchange rates are the official Central Bank of Russia rates as of
> 07.11.2026 (cbr-xml-daily.ru). For production use, fetch them live from the
> CBR JSON feed at startup.

## Tech stack

Scala 3 · BigDecimal · enums · pattern matching.

## License

MIT — see [LICENSE](LICENSE).
