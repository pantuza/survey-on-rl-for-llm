# survey-on-rl-for-llm

**A Survey on Reinforcement Learning for LLM Training**

A compact, tutorial-oriented survey of reinforcement learning applied to
large language model (LLM) training, organized around a three-axis
taxonomy: the **reward signal** that drives learning, the **optimization
algorithm** that updates the policy, and the **training scope**
(single-step preference fine-tuning vs. multi-step agentic trajectories).

Formatted for *IEEE Communications Surveys & Tutorials* using the
`IEEEtran` journal document class.

## Repository layout

All source files live at the repository **root** so the project can be
uploaded to Overleaf directly:

| File | Purpose |
|------|---------|
| `00-main.tex` | Main entry point (preamble, title, abstract, `\input`s) |
| `01-introduction.tex` | Introduction, scope, contributions |
| `02-background.tex` | From LLM RL to Agentic RL; MDP/POMDP; algorithms |
| `03-taxonomy.tex` | The three-axis taxonomy (figure + placement table) |
| `04-reward-signals.tex` | Axis A: reward signal |
| `05-optimization.tex` | Axis B: optimization algorithm |
| `06-agentic-rl.tex` | Axis C: training scope / agentic RL |
| `07-challenges.tex` | Open challenges and future directions |
| `08-conclusion.tex` | Conclusion |
| `references.bib` | BibTeX bibliography |
| `IEEEtran.cls` | IEEE journal document class |

## Building

- **Main document:** `00-main.tex`
- **Compiler:** pdfLaTeX
- **Bibliography:** BibTeX (`\bibliographystyle{IEEEtran}`)

Local build sequence:

```bash
pdflatex 00-main
bibtex   00-main
pdflatex 00-main
pdflatex 00-main
```

## Importing into Overleaf

The files are kept flat at the root precisely so they can be dropped into
Overleaf without any path fixes. Choose one of the two methods below.

### Method A — Upload a ZIP as a new project (recommended)

1. Create a ZIP of the **root files** (not the repository folder itself,
   so that `00-main.tex` sits at the top level of the archive):

   ```bash
   zip survey.zip *.tex *.bib *.cls
   ```

2. In Overleaf, click **New Project → Upload Project** and select
   `survey.zip`.
3. Open **Menu** (top-left) and set:
   - **Main document:** `00-main.tex`
   - **Compiler:** `pdfLaTeX`
4. Click **Recompile**.

### Method B — New blank project, then upload files

1. In Overleaf, click **New Project → Blank Project** and give it a name.
2. Delete the auto-generated `main.tex`.
3. Click the **Upload** icon in the file panel and upload every root file
   (`00-main.tex`, `01-…` through `08-…`, `references.bib`,
   `IEEEtran.cls`).
4. Open **Menu** and set **Main document** to `00-main.tex` and
   **Compiler** to `pdfLaTeX`.
5. Click **Recompile**.

> **Note:** Because all `\input{}` calls use plain, root-relative names
> (e.g. `\input{01-introduction}`) and the bibliography is referenced as
> `\bibliography{references}`, no links break when the files are uploaded
> flat at the project root. `IEEEtran.cls` is included so the project
> compiles even if the class is not pre-installed on the Overleaf TeX
> distribution.
