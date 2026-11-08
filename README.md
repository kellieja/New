# Blog Writer Swarm

Five Claude agents that turn one sentence into a finished blog post.

You describe the post. The agents pass the work down the line, each doing one job, until the Editor approves it.

```
Admin  →  Planner  →  Researcher  →  Writer  ⇄  Editor  →  published post
brief     outline     facts          draft      review
```

## What you need

- Python 3.10 or newer
- An Anthropic API key. Get one at [console.anthropic.com](https://console.anthropic.com/) → API Keys.
- Jupyter, VS Code, or Google Colab to open the notebook

## Run it in 4 steps

**1. Get the code**

```bash
git clone https://github.com/kellieja/New.git
cd New
git checkout ccr-26c2edac-ip5yu7
```

**2. Install the packages**

```bash
pip install -r requirements.txt
```

**3. Add your API key**

Mac / Linux:
```bash
export ANTHROPIC_API_KEY="sk-ant-..."
```

Windows (PowerShell):
```powershell
$env:ANTHROPIC_API_KEY="sk-ant-..."
```

Never paste your key into the notebook or commit it to GitHub.

**4. Open the notebook and run every cell**

```bash
jupyter notebook all_agents_tutorials/blog_writer_swarm.ipynb
```

Then choose **Run → Run All Cells**. You'll see each agent's progress print as it works. The finished post renders at the bottom.

### Using Google Colab instead

1. Go to [colab.research.google.com](https://colab.research.google.com) → **File → Upload notebook** and upload `blog_writer_swarm.ipynb`.
2. Click the key icon in the left sidebar, add a secret named `ANTHROPIC_API_KEY`, and turn on notebook access.
3. Add this cell at the top and run it first:
   ```python
   import os
   from google.colab import userdata
   os.environ["ANTHROPIC_API_KEY"] = userdata.get("ANTHROPIC_API_KEY")
   ```
4. **Runtime → Run all.**

## Write your own post

Find this cell in section 5 and change the sentence:

```python
ws = run_swarm(
    "Write a blog post for small-business owners on why their website isn't "
    "turning visitors into customers, and three fixes they can make this week."
)
```

The more you say about audience, tone, and length, the closer the first draft lands. Anything you leave out, the Admin agent fills in and tells you what it assumed.

To save the result as a file:

```python
open("post.md", "w").write(ws.final)
```

## Settings

At the top of the notebook:

| Setting | Default | What it does |
|---|---|---|
| `MODEL` | `claude-opus-5-5` | Which Claude model runs the agents |
| `EFFORT` | `medium` | `low` is faster and cheaper; `high` gives more polish |
| `USE_WEB_SEARCH` | `False` | `True` lets the Researcher search the live web for facts (extra cost per search) |
| `MAX_TURNS` | `30` | Safety cap so a run can't loop forever |

## How it works

Each agent is a set of instructions plus a few tools. One tool is always a handoff, like `transfer_to_writer`. When an agent calls it, control moves to the next agent along with the shared workspace: brief, outline, research, draft, and editor notes.

The Editor can send a draft back to the Writer up to twice, then makes the final fixes and publishes.

## Cost

Each run makes roughly 8 to 20 API calls, depending on how many edit rounds the Editor asks for. Check your usage at [console.anthropic.com](https://console.anthropic.com/). Set `EFFORT = "low"` while you experiment.

## Troubleshooting

| Error | Fix |
|---|---|
| `AuthenticationError` or "Could not resolve authentication" | Your API key isn't set in the same terminal or kernel. Redo step 3, then restart the notebook kernel. |
| `ModuleNotFoundError: anthropic` | Run `pip install -r requirements.txt` in the same Python environment Jupyter uses. |
| `RateLimitError` | Wait a minute and run again, or lower `EFFORT`. |
| "stopped without handing off" | Rare. Run the cell again. |
