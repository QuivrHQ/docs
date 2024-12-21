# Simple Parser

The Simple Parser provides basic text processing capabilities for straightforward document parsing needs.

## Features

- Basic text chunking
- Minimal preprocessing
- Fast processing speed
- Low memory usage

## Usage

```python
from quivr_core.parsers import SimpleParser

parser = SimpleParser()
documents = parser.parse("path/to/document.txt")

for doc in documents:
    print(f"Content: {doc.page_content}")
```

## Configuration

Configure the parser with these options:

```python
parser = SimpleParser(
    chunk_size=500,  # Number of characters per chunk
    chunk_overlap=50,  # Number of overlapping characters between chunks
    strip_whitespace=True,  # Remove excess whitespace
    lowercase=False  # Convert text to lowercase
)
```

## When to Use

Use the Simple Parser when:
- Processing plain text files
- Need fast processing
- Don't require advanced features
- Working with simple document structures

For more advanced parsing needs, see the [Megaparse](/open-source/parsers/megaparse) documentation.
