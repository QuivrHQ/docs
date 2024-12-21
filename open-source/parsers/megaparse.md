# Megaparse

Megaparse is an advanced document parsing system that can handle complex document structures and multiple file formats.

## Features

- Multi-format support (PDF, DOCX, TXT, etc.)
- Intelligent chunk splitting
- Metadata extraction
- Table and image handling
- Structure preservation

## Usage

```python
from quivr_core.parsers import MegaparseParser

parser = MegaparseParser()
documents = parser.parse("path/to/document.pdf")

for doc in documents:
    print(f"Content: {doc.page_content}")
    print(f"Metadata: {doc.metadata}")
```

## Configuration

You can customize the parser behavior:

```python
parser = MegaparseParser(
    chunk_size=1000,
    chunk_overlap=200,
    include_metadata=True,
    extract_tables=True
)
```

## Supported File Types

- PDF (.pdf)
- Word Documents (.docx, .doc)
- Text Files (.txt)
- Markdown (.md)
- HTML (.html)
- And more...

For simpler parsing needs, see the [Simple Parser](/open-source/parsers/simple) documentation.
