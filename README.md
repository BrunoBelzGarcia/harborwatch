# HarborWatch

HarborWatch reviews security log entries with Qwen Coder. For each entry, it checks the model's JSON response and records a label, severity, and short reason. The Lab 6 notebook writes CSV and JSON results and asks Qwen to draft a Sigma rule from entries it flags. UNKNOWN with severity 0 means the request failed or the reply could not be validated.

## Run Lab 6

1. Place the course's `ssh_auth_log.txt` beside `HarborWatch_Lab6.ipynb` in Jupyter.
2. Run the setup cells to install `openai` and `pyyaml`. Enter the instructor-provided HTTPS API endpoint ending in `/v1`, enter the API key in the hidden prompt, and select the assigned Qwen Coder model.
3. Run the triage and batch cells, then save `triage_results.csv`, `triage_results.json`, and `detection_rule.txt`.

The notebook accepts `QWEN_BASE_URL`, `QWEN_API_KEY`, and `QWEN_MODEL` from the runtime environment. Keep credentials out of the notebook and review logs and outputs for private data before publishing.

## Review the output

Labels help prioritize review. Check each finding against the source event before acting on it. Review the Sigma rule's event source, field mapping, and conditions before using it in a detection system.

The batch treats log text as untrusted input. An offline check verifies that log text stays in a JSON data field. Offline tests also cover fenced JSON, invalid replies, invalid input, and batch ordering.

## Lab 5

`HarborWatch.ipynb` contains the original Windows Security event workflow. `assessment.md` records that run and identifies model claims the Windows CSV could not support.

## License

MIT. See [LICENSE](LICENSE).
