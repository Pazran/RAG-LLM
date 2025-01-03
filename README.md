# RAG-LLM (WIP)

SSE-LLM is a demonstration of using **ServerSent-Events** to stream response directly from a locally hosted Language Model (LLM) like [llamacpp](https://github.com/ggerganov/llama.cpp) or [koboldcpp](https://github.com/LostRuins/koboldcpp), written in Python.

_Note: Currently only the basic interaction with the API endpoint for text generation. RAG not implemented yet. I feel like doing it as a web based application instead of Python._

## Demo Video
This is an example of using the SSE API running KoboldCpp locally
[![CLI SSE Demo](https://github.com/Pazran/RAG-LLM/blob/84e41d105acb16901f524410dd13a52d36ac43c5/demo/sse-demo.gif)](https://github.com/Pazran/RAG-LLM/blob/84e41d105acb16901f524410dd13a52d36ac43c5/demo/sse-demo.gif)

## Future Development
- Retrieval-augmented generation to enhance LLM outputs
- Adding a **vector database** for hybrid search and pure vector-based retrieval, improving knowledge retrieval efficiency.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/RAG-LLM.git
   ```
2. Create virtual environment:
   ```bash
   python -m venv venv
   source ./venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Arguments:

- `--url <URL>`
  - **Description**: The server URL for the SSE (Server-Sent Events) endpoint.
  - **Default**: `http://localhost:5001/api/extra/generate/stream`
  
- `--verbose`
  - **Description**: Enable verbose logging for detailed information during execution.
  - **Default**: Disabled (shows only info level logs)
  
- `--timeout <SECONDS>`
  - **Description**: The timeout duration for the request, in seconds.
  - **Default**: `60` seconds

- `--check-version`
  - **Description**: Check and print the API version from the server.
  - **Example**: If specified, the program will fetch and print the server's API version and then exit without further processing.

- `--check-model`
  - **Description**: Check and print the LLM (Language Model) used by the server.
  - **Example**: If specified, the program will fetch and print the model information and then exit without further processing.

## Example Usage:

Run the application locally:
```bash
python main.py
```

1. **Check API version**:
   ```bash
   python main.py --check-version
   ```

2. **Check LLM model**:
   ```bash
   python main.py --check-model
   ```

3. **Generate Stream Data with Custom URL and Timeout**:
   ```bash
   python main.py --url http://yourserver.com/api/extra/generate/stream --timeout 120
   ```

4. **Enable verbose logging**:
   ```bash
   python main.py --verbose
   ```

5. **Check API version and LLM model**:
   ```bash
   python main.py --check-version --check-model
   ```

## Contributing
Feel free to open issues or submit pull requests to improve the project.

## License
This project is licensed under the [MIT License](LICENSE).
