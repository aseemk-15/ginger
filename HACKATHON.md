# OpenAI AWS hackathon

Private team project based on the `codex-advanced-patterns` branch of
[openai-on-aws/workshop-codex](https://github.com/openai-on-aws/workshop-codex),
starter commit `542c3d5`. The original code and documentation licenses are included.

## Local setup

```sh
cd bedrock-chat
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
pytest -q
```

Use your own workshop AWS credentials, saved outside this repository in a named
AWS profile. Never commit credentials, session tokens, or `.env` files.

On Aseem's machine, launch the configured workshop Codex CLI with:

```sh
codex --profile workshop
```

That profile is stored in `~/.codex/workshop.config.toml` and uses the
`codex-workshop` AWS profile from `~/.aws/credentials`. It selects
`openai.gpt-5.6-sol` on Amazon Bedrock in `us-east-1`. Each teammate must configure
their own local credentials. Workshop credentials expire and need refreshing.

To run the sample application with the same AWS account and workshop model:

```sh
AWS_PROFILE=codex-workshop AWS_REGION=us-east-1 BEDROCK_MODEL_ID=openai.gpt-5.6-sol python -m bedrock_chat
```

Keep the GitHub repository private until the team is ready to submit.
