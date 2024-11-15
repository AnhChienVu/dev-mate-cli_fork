# dev-mate-cli

A command-line tool that leverages OpenAI's Chat Completion API to document code with the assistance of AI models.

Watch this [Demo video](https://youtu.be/YJDD6YBaEFk) to view features.

## Features

- **Source Code Documentation**: Automatically generate comments and documentation for your source code.
- **Multiple File Processing**: Handle one or multiple files in a single command.
- **Model Selection**: Choose which AI model to use with the `--model` flag.
- **Custom Output**: Output the results to a file with the `--output` flag, or display them in the console.
- **Stream Output**: Stream the LLM response to command line with `--stream` flag.

## Usage

### Basic Usage

To run the tool, specify one or more source files or folders as input:

```bash
npm start ./examples/file.js
```

For processing multiple files:

```bash
npm start ./examples/file.js ./examples/file.cpp
```

For processing folders:

```bash
npm start ./examples
```

### Command-line Options

Note: Use `npm start -- -option` to pass the option flag to the program, as npm captures it without the `--`.

- `-m, --model <model-name>`: Choose the AI model to use `(default: google/gemma-2-9b-it:free from OpenRouter)`.

  ```bash
  npm start file.js -- -m "openai/gpt-4o-mini"
  ```

- `-o, --output <output-file>`: Write the output to a specified file.

  ```bash
  npm start file.js -- -o output.js
  ```

- `-t, --temperature <value>`: Set the creativity level of the AI model `(default: 0.7)`.

  ```bash
  npm start file.js -- -t 1.1
  ```

- `-u, --token-usage`: Display token usage information

  ```bash
  npm start file.js -- -u
  ```

- `-s, --stream`: Stream response to command line

  ```bash
  npm start file.js -- -s
  ```

### Additional Commands

- **Check Version:** To check the current version of the tool, use:
  ```bash
  npm start -- --version
  ```
- **Help:** Display the help message listing all available options:
  ```bash
  npm start -- --help
  ```

### Examples

- **Document a JavaScript file and save the result:**

  ```bash
  npm start ./examples/file.js -- --output file-documented.js --model google/gemini-flash-8b-1.5-exp
  ```

- **Process multiple files and print output to the console:**

  ```bash
  npm start ./examples/file.js ./examples/file.py --model google/gemini-flash-8b-1.5-exp
  ```

## Environment Variables

You can store your api key and base url in a `.env` file created at the root of the project. Example configuration:

```makefile
API_KEY=your_api_key
BASE_URL=https://api.openai.com/v1
```

This setup will also allow you to customize other settings, like temperature or base URL, directly in the `.env` file.

## Contributing

Contributions are welcome! If you find a bug or have an idea for an improvement, feel free to [open an issue](https://github.com/mayank-Pareek/dev-mate-cli/issues) or submit a pull request, view [Contribution Guidelines](CONTRIBUTING.md) for more details.

## License

This project is licensed under the [MIT License](LICENSE).
