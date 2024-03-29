# Setting up Claude 3 Haiku in AutoGen 2

In this post, I'll show you how to set up Claude 3 Haiku in AutoGen 2 step-by-step.

## Prerequisites

- Anaconda installed
- Git installed
- Anthropic API key

## Step-by-Step Guide

1. **Create an Anaconda environment**:
   ```
   conda create -n claude-autogen python=3.11
   ```

2. **Activate the Anaconda environment**:
   ```
   conda activate claude-autogen
   ```

3. **Install PyAutogen**:
   ```
   pip install pyautogen
   ```
   
4. **Install AutoGenStudio**:
   ```
   pip install autogenstudio
   ```

5. **Install Poetry**:
   ```
   pip install Poetry
   ```

6. **Download and install LiteLLM**:
   ```
   git clone https://github.com/BerriAI/litellm.git
   ```


7. **Navigate to the litellm subdirectory and modify the "\_\_init\_\_.py" file**:
   ```
   cd litellm/litellm
   ```
   - Edit \_\_init\_\_.py
   - Find the line that says `modify_params = False`
   - Change it to `modify_params = True`
  
8. **Install LiteLLM**
   ```
   cd ..
   poetry install
   pip install -r requirements.txt
   ```

9. **Load the Anthropic API key into the environment (example api-key use your own)**:
   ```
   export ANTHROPIC_API_KEY="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"
   ```

10. **Start AutoGenStudio**:
   ```
   autogenstudio ui
   ```

11. **Start LiteLLM in a separate terminal (with conda activate claude-autogen)**:
   ```
   litellm --model claude-3-haiku-20240307
   ```

12. **Configure the new model in AutoGenStudio**:
   - Browse 127.0.0.1:8081 (can be different, depending on what is displayed in the terminal for AutoGen)
   - Go to "Build" > "Models" > "New Model"
   - Enter the following values:
     - Model: `claude-3-haiku-20240307`
     - API Key: `anything`
     - Base URL: `http://0.0.0.0:4000`
   - Save the configuration

After completing these steps, you have successfully set up Claude 3 Haiku in AutoGen 2 and can now use it now.

## Anthropic Rate Limits

Please note that when using the Claude-3-Haiku model, you may encounter rate limits on the Anthropic side. If you receive the error code 429, it means you have reached the rate limits.

These limits can be increased with the first payment and after waiting periods. You can find more information about this in the Anthropic documentation: https://docs.anthropic.com/claude/reference/rate-limits

If you have problems with the rate limits, I recommend contacting the Anthropic support directly to find a solution.

After completing these steps, you have successfully set up Claude 3 Haiku in AutoGen 2 and can now use it.
