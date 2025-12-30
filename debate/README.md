# Debate Crew

Welcome to the **Debate Crew** project, powered by [crewAI](https://crewai.com). This system uses multiple AI agents to debate a given motion from both sides and then provides a logical decision on the winner based on the arguments presented.

## Installation

Ensure you have Python >=3.10 <3.14 installed on your system. This project uses [UV](https://docs.astral.sh/uv/) for dependency management.

1. Install uv:
   ```bash
   pip install uv
   ```

2. Navigate to your project directory and install the dependencies:
   ```bash
   crewai install
   ```

## Configuration

This project is configured to use **Ollama** by default.

- **LLM Settings**: The default model is `ollama/gpt-oss:20b` (configured in `src/debate/crew.py`).
- **Agents**: Defined in `src/debate/config/agents.yaml`.
- **Tasks**: Defined in `src/debate/config/tasks.yaml`.

### Customizing the Debate

To change the topic of the debate, modify the `motion` input in `src/debate/main.py`:

```python
inputs = {
    'motion': 'There needs to be strict laws to regulate LLMs',
}
```

## Running the Project

To start the debate, run the following command from the root folder:

```bash
crewai run
```

### Output

The crew will generate three separate markdown files in the `output/` directory:
- `output/propose.md`: The argument in favor of the motion.
- `output/oppose.md`: The argument against the motion.
- `output/decide.md`: The final decision by the judge.

## Understanding Your Crew

The Debate Crew is composed of two specialized agents:

1.  **Debater**: Responsible for formulating both the "Propose" and "Oppose" arguments based on the motion.
2.  **Judge**: A fair arbiter that reviews both arguments and decides on a winner based purely on the merits of the points presented.

### Workflow
1.  **Propose**: The Debater creates a compelling argument *for* the motion.
2.  **Oppose**: The Debater creates a compelling argument *against* the motion.
3.  **Decide**: The Judge reviews both arguments and makes a final ruling.

## Support

For support or questions regarding crewAI:
- Visit the [documentation](https://docs.crewai.com)
- [Join our Discord](https://discord.com/invite/X4JWnZnxPb)
- [Chat with our docs](https://chatg.pt/DWjSBZn)
