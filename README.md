# HuggingFace Daily Papers MCP Server

A MCP (Model Context Protocol) server for fetching HuggingFace daily papers.

## Features

- Fetch today's, yesterday's or specific date HuggingFace papers
- Provides paper title, authors, abstract, tags and other details
- Includes paper links and PDF download links
- Supports MCP tools and resource interfaces
- Complete error handling and logging
- Comprehensive test cases

## Installation & Usage

### Option 1: Direct execution with uvx (Recommended)

Install and run directly using uvx:

```bash
uvx huggingface-daily-paper-mcp
```

This will automatically install the package and its dependencies, then start the MCP server.

### Option 2: Local development

For local development, clone the repository and install dependencies:

```bash
git clone https://github.com/huangxinping/huggingface-daily-paper-mcp.git
cd huggingface-daily-paper-mcp
uv sync
```

### Local usage commands

**Run as MCP Server (for development)**:
```bash
python main.py
```

**Test Scraper Function**:
```bash
python scraper.py
```

**Run Tests**:
```bash
uv run -m pytest test_mcp_server.py -v
```

**Build Package**:
```bash
uv run -m build
```

## MCP Interface

### Tools

1. **get_papers_by_date**
   - Description: Get HuggingFace papers for a specific date
   - Parameters: `date` (YYYY-MM-DD format)

2. **get_today_papers**
   - Description: Get today's HuggingFace papers
   - Parameters: None

3. **get_yesterday_papers**
   - Description: Get yesterday's HuggingFace papers
   - Parameters: None

### Resources

1. **papers://today**
   - Today's papers JSON data

2. **papers://yesterday**
   - Yesterday's papers JSON data

## Project Structure

```
huggingface-daily-paper-mcp/
├── main.py                    # MCP server main program
├── scraper.py                 # HuggingFace papers scraper module
├── test_mcp_server.py         # MCP server test cases
├── README.md                  # Project documentation
├── .gitignore                 # Git ignore file
├── pyproject.toml             # Project configuration file
└── uv.lock                    # Dependency lock file
```

## Tech Stack

- **Python 3.10+**: Programming language
- **MCP**: Model Context Protocol framework
- **Requests**: HTTP request library
- **BeautifulSoup4**: HTML parsing library
- **pytest**: Testing framework
- **uv**: Python package manager

## Development Standards

- Use uv native commands for package management
- Follow Python PEP 8 coding standards
- Include type hints and docstrings
- Complete error handling and logging
- Write unit tests to ensure code quality

## Example Output

```json
{
  "title": "Example Paper Title",
  "authors": ["Author One", "Author Two"],
  "abstract": "This is an example abstract...",
  "tags": ["machine-learning", "nlp"],
  "url": "https://huggingface.co/papers/example",
  "pdf_url": "https://arxiv.org/pdf/example.pdf",
  "scraped_at": "2024-01-01T12:00:00"
}
```

## License

MIT License