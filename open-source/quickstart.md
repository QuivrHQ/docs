# Quick start

If you need to quickly start talking to your list of files, here are the steps.

1. Add your API Keys to your environment variables
```python
import os
os.environ["OPENAI_API_KEY"] = "myopenai_apikey"

```
Check our `.env.example` file to see the possible environment variables you can configure. Quivr supports APIs from Anthropic, OpenAI, and Mistral. It also supports local models using Ollama.

2. Create a Brain with Quivr default configuration
```python
from quivr_core import Brain

brain = Brain.from_files(name = "my smart brain",
                        file_paths = ["/my_smart_doc.pdf", "/my_intelligent_doc.txt"],
                        )

```

3. Launch a Chat
```python
brain.print_info()

from rich.console import Console
from rich.panel import Panel
from rich.prompt import Prompt

console = Console()
console.print(Panel.fit("Ask your brain !", style="bold magenta"))

while True:
    # Get user input
    question = Prompt.ask("[bold cyan]Question[/bold cyan]")

    # Check if user wants to exit
    if question.lower() == "exit":
        console.print(Panel("Goodbye!", style="bold yellow"))
        break

    answer = brain.ask(question)
    # Print the answer with typing effect
    console.print(f"[bold green]Quivr Assistant[/bold green]: {answer.answer}")

    console.print("-" * console.width)

brain.print_info()
```

And now you are all set up to talk with your brain !

## Custom Brain
If you want to change the language or embeddings model, you can modify the parameters of the brain.

Let's say you want to use a LLM from Mistral and a specific embedding model :
```python
from quivr_core import Brain
from langchain_core.embeddings import Embeddings

brain = Brain.from_files(name = "my smart brain",
                        file_paths = ["/my_smart_doc.pdf", "/my_intelligent_doc.txt"],
                        llm=LLMEndpoint(
                            llm_config=LLMEndpointConfig(model="mistral-small-latest", llm_base_url="https://api.mistral.ai/v1/chat/completions"),
                        ),
                        embedder=Embeddings(size=64),
                        )
```

Note: The Embeddings class from LangChain lets you choose from a large variety of embedding models. You can configure different models like OpenAI, Cohere, or HuggingFace embeddings based on your needs.

## Launch with Chainlit

If you want to quickly launch an interface with streamlit, you can simply do at the root of the project :
```bash
cd examples/chatbot /
rye sync /
rye run chainlit run chainlit.py
```
For more details, check out our [Chatbot Example](/open-source/examples/chatbot) guide.

Note : Modify the Brain configs directly in examples/chatbot/main.py;
