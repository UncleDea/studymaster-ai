# StudyMaster AI

Turns one public web page into a grounded study pack — an outline, a study section, and a lesson with questions you can answer and have graded. Longer sessions also produce a lab, a project and a runbook.

Every sentence in a pack has to be supported by the source page. A sentence whose quote cannot be found is rewritten once; if it still fails, the pack says plainly that the source does not cover it. The aim is a study pack that never quietly invents material.

## What it does

- Reads one public page and writes a pack sized to the minutes you choose
- Verifies each sentence against the source, rewriting or dropping what it cannot support
- Asks questions, grades answers, and returns a score with a hint before the answer
- Saves packs locally and searches them by title, goal, level, score, minutes or progress
- Exports a pack as Markdown or Word
- Reopening a saved pack makes no model call, so it costs nothing

## Running it

The application lives in `docs/studymaster-ai`.

```
cd docs/studymaster-ai
streamlit run app.py
```

Copy `.env.example` to `.env` and set `OPENAI_API_KEY` before the first run. The page opens at http://localhost:8501.

The full first-visit procedure is in [docs/studymaster-ai/SOP.md](docs/studymaster-ai/SOP.md), and the usage guide is in [docs/studymaster-ai/README.md](docs/studymaster-ai/README.md).

## Checking it

```
python scripts/check_app.py
```

Walks the whole study path against a fake page and runs the test suite without spending API credit. Add `--live` to read one real page and write one real pack in a temporary database, which costs about a cent.

## Stack

Python · Streamlit · OpenAI API · SQLite
