# Quandris Lens Titanic Measurement Analysis

Reproduce the graphs and comparison tables for the Titanic measurement study by Larry Brader, Quandris Inc.

The study compares four anonymized candidate solutions across nine Information Circuits using the same 418 passengers. It includes 126 measurement scenarios: 36 candidate runs and 90 baseline runs, with ten baseline repetitions per circuit.

**[Read the full report and download the PDF](https://quandris.com/titanic-measurement-analysis-report/)** · **[Sources and reproducibility](https://quandris.com/sources-reproducibility/)**

## What this repository provides

The JupyterLab notebook rebuilds measurement tables and graphs from captured Quandris Lens JSON telemetry. It makes the calculations available for inspection and reproduction.

The analysis examines three connected outputs:

- **Position:** candidate position differences from the corresponding baseline.
- **Information Force contributions:** differences in configured and recorded forces associated with the declared passenger relationships.
- **Boundary and uncertainty:** measured positions relative to the configured survival/death boundary, including geometric proximity.

These are measurements within the external Quandris Lens procedure. The notebook analyzes recorded telemetry; it does not rerun the original Lens simulations or the candidate models. Original candidate notebooks and prediction submissions are excluded from this package.

## Get started

Use **Python 3.12** and **JupyterLab 4 or later**.

1. Clone this repository, or choose **Code → Download ZIP** on GitHub and extract it.
2. Open a terminal in the folder containing `Titanic_Lens_Publication_Review.ipynb` and `requirements.txt`. Keep the notebook, Python scripts, `data/` and `graphs/` together.
3. Install the dependencies and launch the notebook:

```sh
python -m pip install -r requirements.txt
python -m jupyterlab Titanic_Lens_Publication_Review.ipynb
```

4. In JupyterLab, select the **Run Analysis** code cell and press **Ctrl+Enter**.
5. Leave the cell running until the progress panel reports **COMPLETE**. The results appear in the notebook and are saved in `graphs/`.

Run the notebook with the Python environment in which you installed the requirements. If the panel reports **STOPPED**, read the displayed error, correct the missing dependency or input, and rerun the cell.

## Repository guide

| File or folder | Purpose |
| --- | --- |
| `Titanic_Lens_Publication_Review.ipynb` | Main notebook for running the analysis and viewing results |
| `run_analysis.py` | Coordinates input checks, calculations, graph generation and progress reporting |
| `telemetry_analysis.py` | Converts captured telemetry into measurement tables |
| `titanic_publication_graphs.py` | Generates the report graphs |
| `validate_package.py` | Checks data coverage, calculations and expected outputs |
| `requirements.txt` | Python dependencies |
| `data/telemetry/` | Baseline and anonymized candidate telemetry |
| `data/calibration/BaselineMeasurements.json` | Captured baseline calibration reference |
| `graphs/` | Calculated CSV tables and generated figures |
| `docs/GRAPH_READING_GUIDE.md` | Guide to interpreting the graphs |

## Results and validation

A successful run generates **six CSV tables and thirteen PNG images covering twelve graph topics**. Graph 6 has two parts. Existing calculated outputs in `graphs/` are replaced; source telemetry is retained.

For an additional technical check, run:

```sh
python validate_package.py
```

Review the reported `technical_checks_passed` value and any errors. These checks verify technical consistency; they do not constitute independent replication or establish validity across other domains.

The report provides the supporting explanations:

- **Appendix A:** source data and selected runs.
- **Appendix B:** baseline calibration and companion workbook.
- **Appendix C:** graph calculations and telemetry mappings.
- **Appendix D:** reproduction and validation.
- **Appendix E:** glossary.

## Citation

Brader, Larry. (2026). *Quandris Lens Titanic Measurement Analysis*. Version 1.0. Quandris Inc. Published 24 November 2026. https://quandris.com/titanic-measurement-analysis-report/

## License

Consult the repository's license file for the applicable terms. Third-party materials remain subject to their respective licenses.

