# ThesisLab

Every thesis is a falsifiable experiment. Paper trading only.

ThesisLab turns a plain-English investment thesis into a testable paper-trading experiment, built in n8n for NYU Stern OPMG-UB 30-001 (Foundations of AI Agents).
Arthur Voss, a fictional old-school Wall Street researcher (disciplined, skeptical, evidence-driven, slightly contrarian), is the research partner. The character affects tone only; it never overrides safety rules or data requirements.

## Guardrails
- Alpaca **paper** trading only. No live endpoint, no live credentials.
- No order without explicit human approval (APPROVE <experiment id>).
- V1 is long-only U.S. equities. No options, leverage, shorts, or crypto.
- Prices, fills and results come only from tools. Nothing is invented.
- Failures fail closed and alert the owner.

## Workflows
| Workflow | State | File |
|---|---|---|
| ThesisLab - Live Board | Published | [workflows/live-board.json](workflows/live-board.json) |
| ThesisLab - Email Gateway | Published | [workflows/email-gateway.json](workflows/email-gateway.json) |
| ThesisLab - Error Alerts | Published | [workflows/error-alerts.json](workflows/error-alerts.json) |
| ThesisLab - GitHub Backup | Draft | [workflows/github-backup.json](workflows/github-backup.json) |
| ThesisLab - SMS Gateway | Published | [workflows/sms-gateway.json](workflows/sms-gateway.json) |
| ThesisLab - Telegram Gateway | Published | [workflows/telegram-gateway.json](workflows/telegram-gateway.json) |
| ThesisLab - Thesis to Paper-Trade Experiment | Published | [workflows/thesis-to-paper-trade-experiment.json](workflows/thesis-to-paper-trade-experiment.json) |

## Data
- data/thesislab_experiments.json and .csv: every thesis, bet, order status and verdict (email signatures and phone numbers stripped).
- Personal contact details (allowlisted emails, phone numbers, Telegram IDs) are masked as [redacted-...] in the workflow files.
- data/schema.json: column definitions for the n8n data table.

## Restoring
In n8n, create a workflow, open the menu, choose Import from File and pick a file from workflows/. Credentials are referenced by name only; reconnect your own Alpaca (paper), OpenAI, Pinecone, Gmail, Telegram and Twilio accounts after import. No API keys are stored in this repository.

_Last synced 2026-10-11 06:07 ET by the ThesisLab - GitHub Backup workflow._
