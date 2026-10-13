# Run the Kalman filter notebook locally

## Start Jupyter

Open a terminal and run:

```sh
source /Users/federico/miniforge3/etc/profile.d/conda.sh
conda activate kf_bf
cd "/Users/federico/Desktop/13_minverva_humanoids/RESEARCH /Kalman-and-Bayesian-Filters-in-Python"
jupyter notebook --notebook-dir="$PWD" --port=8888 --port-retries=0 04-One-Dimensional-Kalman-Filters.ipynb
```

The `kf_bf` environment already exists on this computer. The quoted folder
path is intentional: `RESEARCH ` has a trailing space in its name.

Keep the terminal running. Jupyter opens a browser; the notebook is available at:

<http://localhost:8888/notebooks/04-One-Dimensional-Kalman-Filters.ipynb>

If Jupyter asks for a token, open the URL containing `?token=...` printed in
the terminal first. Authentication remains enabled.

Run cells in order with **Shift+Enter**. Opening the notebook alone does not
execute its code. Restarting the kernel clears variables, so rerun prerequisite
cells afterward.

## Where edits are saved

Yes: with the command above, browser edits are saved directly to
`04-One-Dimensional-Kalman-Filters.ipynb` in this repository folder.
Use **File → Save Notebook** or the save button before closing. Jupyter also
autosaves; check that the save completed.

Saved content includes code, Markdown, and cell outputs. In-memory Python
variables are not saved as a running session. Saving does not commit changes
to Git or upload them to GitHub.

To see local changes, run this in a second terminal from the repository folder:

```sh
git status --short
git diff --stat -- 04-One-Dimensional-Kalman-Filters.ipynb
```

## Stop Jupyter

Save the notebook, then press **Ctrl+C** in the server terminal and confirm
shutdown if prompted. Closing the browser tab alone does not stop the server.

## If port 8888 is already in use

The command fails instead of silently switching to another port. If an
existing Jupyter server serves this same folder, use its notebook URL.
Otherwise, stop that server from its original terminal before starting this
one. An alternative port changes the URL:

```sh
jupyter notebook --notebook-dir="$PWD" --port=8889 --port-retries=0 04-One-Dimensional-Kalman-Filters.ipynb
```

Then open <http://localhost:8889/notebooks/04-One-Dimensional-Kalman-Filters.ipynb>.

## Setup on a computer without the environment

With Conda installed, run these once from this repository folder:

```sh
conda env update -f environment.yml
conda activate kf_bf
```

Then use the Jupyter command above.

Reference: [Jupyter Notebook documentation](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html).
