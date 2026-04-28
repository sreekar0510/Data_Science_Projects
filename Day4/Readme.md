# NumPy Stock Market Analyzer

A hands-on NumPy project that simulates and analyzes one year of stock price data for 5 Indian equities — built to practice every core NumPy concept.

## Concepts Covered

| Concept | Where used |
|---|---|
| Array creation & dtypes | `float32` price matrix, `np.zeros`, `np.array` |
| Slicing & axis indexing | Per-stock column slices `prices[:, i]` |
| Reshaping & flattening | 30-day rolling volatility windows |
| Boolean masking | Crash-day detection |
| Fancy indexing | Top-5 gain days with `np.argpartition` |
| Vectorization | Price series, cumulative returns — no loops |
| Broadcasting | Normalisation `(prices - mean) / std` |
| Math functions | `mean`, `std`, `corrcoef`, `argmax`, `cumsum`, `diff` |

## Project Structure

```
numpy-stock-analyzer/
├── analyzer.py          # Main analysis script
├── tests/
│   └── test_analyzer.py # Pytest unit tests
├── requirements.txt
└── README.md
```

## Setup & Run

```bash
# Install dependencies
pip install -r requirements.txt

# Run the analyzer
python analyzer.py

# Run tests
python -m pytest tests/ -v
```

## Sample Output

```
════════════════════════════════════════════════════════════
  NumPy Stock Market Analyzer
════════════════════════════════════════════════════════════

Data shape : (252, 5)  → (days × stocks)
dtype      : float32
Memory     : 5,040 bytes  (vs ~10,080 bytes in float64)

── Daily Return Stats ──
  INFY         mean=+0.047%  std=1.493%  max=+4.51%  min=-3.89%
  ...

── Annual Cumulative Return ──
  INFY         +13.24%
  ...
  🏆 Best  performer : NTPC  (+18.41%)
  ⚠️  Worst performer : SUNPHARMA  (-2.11%)
```