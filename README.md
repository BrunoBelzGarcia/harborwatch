# HarborWatch

HarborWatch uses the class Qwen Coder model to classify a small sample of Windows security events as BENIGN, SUSPICIOUS, or MALICIOUS, with a short reason. UNKNOWN flags replies that fail format validation.

## Run the notebook

Open `HarborWatch.ipynb` in Jupyter and run its cells in order. Install the OpenAI client, enter the instructor-provided API base URL, enter the API key in the hidden prompt, and select the assigned Qwen Coder model. The university network or VPN may be required. Never hardcode an API key.

Export your own Security log from Windows Event Viewer as `security_log.csv` and keep it beside the notebook in your private Jupyter workspace. The notebook processes up to 20 complete CSV events and writes `assessment.md`. UTF-8, UTF-16 with a byte-order mark, and Windows-1252 exports are supported.

## Example assessment and limitations

The included assessment was generated using `qwen3-coder-next` from a 20-event sample: 20 BENIGN, 0 SUSPICIOUS, 0 MALICIOUS, and 0 UNKNOWN. The CSV contains metadata rather than complete event descriptions. The report includes a review note identifying unsupported details in some model explanations. These results do not establish that the computer is secure or that the sampled activity was authorized.

The model uses temperature 1.0 and top_p 0.95, so results may vary between runs. A person must validate labels and explanations against the original events. This tool does not block activity or remediate incidents.

## Privacy

Raw logs and API keys are excluded from this repository. The public notebook has cleared outputs to prevent accidental disclosure. Review every generated report for personal information before publishing it.

## AI assistance

ChatGPT helped repair the starter notebook, implement and review the code, and explain the findings. Qwen Coder provided design advice and performed the live classifications. The notebook contains a design prompt so this step can be reproduced with authorized access.
