# Formula Documentation Project

A Quarto-based documentation project for mathematical formulas and financial models, using SymPy for symbolic mathematics.

## Features

- **Quarto**: Reproducible, publication-quality documentation
- **SymPy**: Symbolic mathematics for formula verification
- **Jupyter Engine**: Python-based computation
- **HTML Output**: Clean, navigable web documentation

## Current Content

- **G2++ Interest Rate Model**: Two-factor Gaussian model with:
  - Core stochastic differential equations
  - Zero-coupon bond pricing formulas
  - SymPy implementation and verification
  - Numerical examples with typical parameters

## Setup

### Prerequisites

- Python 3.8 or higher
- Quarto CLI ([installation guide](https://quarto.org/docs/get-started/))

### Installation

1. Clone this repository:
```bash
git clone <your-repo-url>
cd <repo-name>
```

2. Install Python dependencies:
```bash
pip install -r requirements.txt
```

### Usage

#### Preview (development mode)
```bash
quarto preview
```

This will start a local server and open the documentation in your browser. Changes to `.qmd` files will automatically refresh.

#### Render (build static site)
```bash
quarto render
```

The rendered HTML files will be in the `_site/` directory.

## Project Structure

```
.
├── _quarto.yml           # Quarto configuration
├── index.qmd             # Home page
├── g2pp_model.qmd        # G2++ model documentation
├── styles.css            # Custom CSS styles
├── requirements.txt      # Python dependencies
└── README.md            # This file
```

## Adding New Documents

1. Create a new `.qmd` file in the project root
2. Add it to the navbar in `_quarto.yml`:
```yaml
website:
  navbar:
    left:
      - href: your_new_doc.qmd
        text: Your Title
```
3. Write your content with Python code chunks using SymPy

## Example Code Chunk

````markdown
```{python}
import sympy as sp
x = sp.symbols('x')
expr = sp.sin(x)**2 + sp.cos(x)**2
simplified = sp.simplify(expr)
print(f"sin²(x) + cos²(x) = {simplified}")
```
````

## License

[Your chosen license]

## Contributing

[Your contribution guidelines]
