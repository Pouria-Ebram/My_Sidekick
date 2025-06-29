# My Sidekick - Personal AI Co-worker

A sophisticated multi-agent AI assistant that uses structured outputs and advanced workflow management to help you complete tasks efficiently. Built with LangChain, LangGraph, and Gradio.

## 🚀 Features

- **Multi-Agent Workflow**: Uses a worker-evaluator pattern for intelligent task completion
- **Structured Outputs**: Pydantic-based evaluation system for consistent feedback
- **Web Automation**: Playwright integration for web scraping and automation
- **Calendar Integration**: Google Calendar event creation and management
- **Push Notifications**: Pushover integration for real-time notifications
- **Interactive UI**: Beautiful Gradio interface for seamless interaction
- **Memory Management**: Persistent conversation history with thread management

## 🏗️ Architecture

The system uses a sophisticated graph-based workflow:

1. **Worker Node**: Processes user requests using available tools
2. **Tools Node**: Executes web automation, calendar operations, and notifications
3. **Evaluator Node**: Assesses task completion and provides structured feedback
4. **Router Logic**: Intelligently routes between nodes based on tool usage and evaluation results

## 📋 Prerequisites

- Python 3.8+
- OpenAI API key
- Google Calendar API credentials (optional)
- Pushover credentials (optional)

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd My_Sidekick
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv venv
   .\venv\Scripts\Activate.ps1  # Windows
   source venv/bin/activate     # Linux/Mac
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Install Playwright browsers**
   ```bash
   python -m playwright install
   ```

5. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   GOOGLE_CLIENT_ID=your_google_client_id
   GOOGLE_CLIENT_SECRET=your_google_client_secret
   GOOGLE_PROJECT_ID=your_google_project_id
   GOOGLE_REDIRECT_URI=your_redirect_uri
   PUSHOVER_TOKEN=your_pushover_token
   PUSHOVER_USER=your_pushover_user
   ```

## 🔧 Setup

### Google Calendar Integration (Optional)

1. Set up a Google Cloud Project and enable the Google Calendar API
2. Create OAuth 2.0 credentials
3. Add your credentials to the `.env` file
4. Run the authentication cell in the notebook once to create `token.pkl`

### Pushover Notifications (Optional)

1. Create a Pushover account
2. Get your user key and app token
3. Add them to the `.env` file

## 🚀 Usage

1. **Start Jupyter Lab**
   ```bash
   jupyter lab
   ```

2. **Open the notebook**
   - Open `sidekick_notebook.ipynb`
   - Run all cells to initialize the system

3. **Launch the UI**
   - The final cell will launch a Gradio interface
   - Access it at `http://127.0.0.1:7860`

4. **Interact with your Sidekick**
   - Enter your request in the message box
   - Define success criteria for your task
   - Click "Go!" to start processing

## 🎯 How It Works

### Task Processing Flow

1. **User Input**: You provide a task and success criteria
2. **Worker Processing**: The AI worker analyzes the task and uses available tools
3. **Tool Execution**: Web automation, calendar operations, or notifications are performed
4. **Evaluation**: The evaluator assesses if the task meets your success criteria
5. **Feedback Loop**: If criteria aren't met, the worker tries again with feedback
6. **Completion**: Task is marked complete when success criteria are satisfied

### Available Tools

- **Web Automation**: Browse websites, extract information, fill forms
- **Calendar Management**: Create and manage Google Calendar events
- **Push Notifications**: Send real-time notifications via Pushover
- **General AI**: Answer questions and provide information

## 📁 Project Structure

```
My_Sidekick/
├── sidekick_notebook.ipynb    # Main application notebook
├── requirements.txt           # Python dependencies
├── .env                      # Environment variables (create this)
├── token.pkl                 # Google Calendar auth token (auto-generated)
├── venv/                     # Virtual environment
└── README.md                 # This file
```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `OPENAI_API_KEY` | Your OpenAI API key | Yes |
| `GOOGLE_CLIENT_ID` | Google OAuth client ID | No |
| `GOOGLE_CLIENT_SECRET` | Google OAuth client secret | No |
| `GOOGLE_PROJECT_ID` | Google Cloud project ID | No |
| `GOOGLE_REDIRECT_URI` | OAuth redirect URI | No |
| `PUSHOVER_TOKEN` | Pushover app token | No |
| `PUSHOVER_USER` | Pushover user key | No |

## 🛠️ Customization

### Adding New Tools

1. Create a new function for your tool
2. Wrap it with `StructuredTool.from_function()`
3. Add it to the `all_tools` list
4. The system will automatically integrate it

### Modifying Success Criteria

The evaluator uses structured outputs to assess task completion. You can modify the `EvaluatorOutput` class to add new evaluation criteria.

## 🐛 Troubleshooting

### Common Issues

1. **Playwright Errors**: Ensure browsers are installed with `python -m playwright install`
2. **Google Calendar Auth**: Run the authentication cell once to create `token.pkl`
3. **Missing Dependencies**: Check that all packages in `requirements.txt` are installed
4. **API Key Issues**: Verify your OpenAI API key is valid and has sufficient credits

### Debug Mode

Set `headless=False` in the Playwright browser creation to see browser automation in action.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Built with [LangChain](https://langchain.com/) and [LangGraph](https://langchain.com/langgraph)
- UI powered by [Gradio](https://gradio.app/)
- Web automation with [Playwright](https://playwright.dev/)
- Calendar integration via [Google Calendar API](https://developers.google.com/calendar)

## 📞 Support

If you encounter any issues or have questions, please open an issue on the GitHub repository.

---

**Happy coding with your AI Sidekick! 🤖✨** 