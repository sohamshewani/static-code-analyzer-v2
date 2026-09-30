Static Code Analyzer README

## Overview
Static Code Analyzer is a multi-faceted CLI utility designed to perform static code analysis on Python projects, identify dead code, redundant imports, and unused functions, and concurrently test API endpoints for performance and reliability. It leverages abstract syntax tree (AST) and asynchronous concurrency, with findings and historical performance data stored in an SQLite database.

## Files
- **src/core.py**: Core logic for static analysis and API testing.
- **src/cli.py**: CLI interface with rich terminal output.
- **tests/test_core.py**: Unit tests for core functionality.
- **README.md**: This document.

## Architecture
1. **Static Code Analysis**
   - **AST Inspection**: Uses `astroid` to parse and analyze Python code.
   - **Dead Code Detection**: Identifies unused functions and redundant imports.
   - **Code Logging**: Stores analysis results in a SQLite database.
2. **API Testing**
   - **Concurrent Testing**: Uses `aiohttp` for asynchronous endpoint testing.
   - **Performance Metrics**: Tracks response times and status codes.
   - **Logging**: Records test results in the same database.

## Installation
```bash
pip install click astroid pytest aiohttp rich sqlite3 astunparse asyncio
```

## Running the Tool
```bash
python src/cli.py [options]
```

### Options
- `-p`, `--path`: Path to the Python project directory.
- `-a`, `--api-endpoints`: Path to a file containing API endpoints (e.g., `api_endpoints.txt`).
- `-o`, `--output`: Path to save the analysis report.

## Example Usage
```bash
python src/cli.py -p ./my_project -a ./api_endpoints.txt -o ./analysis_report.txt
```

## Tests
To run tests, navigate to the `tests` directory and execute `pytest`.

## Contributing
Fork the repository and submit a pull request. Contributions are welcome!

## License
This project is licensed under the MIT License.

## Contact
For any questions, reach out to the maintainer via the GitHub issue tracker.