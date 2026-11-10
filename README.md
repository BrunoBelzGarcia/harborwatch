# HarborWatch

HarborWatch sends a small sample of Windows Security events to Qwen Coder and returns BENIGN, SUSPICIOUS, or MALICIOUS labels with short explanations. UNKNOWN means a reply failed the format checks.

## Run it

Open `HarborWatch.ipynb` in Jupyter and run the cells in order. Enter the API address supplied by your instructor, enter the key in the hidden prompt, and choose the assigned Qwen Coder model. Access may require the university network or VPN.

Export the Security log from Windows Event Viewer as `security_log.csv` and put it beside the notebook in your private Jupyter workspace. The notebook reads up to 20 complete CSV records and writes `assessment.md`. It supports UTF-8, UTF-16 with a byte-order mark, and Windows-1252 files.

## Results and review

The included report records a live run with `qwen3-coder-next`: 20 events labeled BENIGN and none labeled SUSPICIOUS, MALICIOUS, or UNKNOWN. The export contains event metadata without full descriptions. Some Qwen explanations assume account or process details that the CSV does not contain; the report identifies those claims as unsupported. These results do not establish that the computer is secure or that the activity was authorized.

The model uses temperature 1.0 and top_p 0.95, so another run may produce different answers. Review the original events before acting on a label. HarborWatch does not change system settings or block activity.

## Keep private data out of GitHub

This repository excludes raw logs and API keys. Notebook outputs are cleared in the public copy. Check generated reports for personal details before publishing them.

## AI assistance

ChatGPT helped repair the starter notebook, write and review the code, and prepare the explanations. Qwen provided design advice and classified the events in the live run. The notebook includes the design prompt used for that step.
