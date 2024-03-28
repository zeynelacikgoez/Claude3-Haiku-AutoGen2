# Setting up Claude 3 Haiku in AutoGen 2

In this post, I'll show you how to set up Claude 3 Haiku in AutoGen 2 step-by-step.

## Prerequisites

- Anaconda installed
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

4. **Install LiteLLM**:
   ```
   pip install litellm
   ```

5. **Start AutoGenStudio**:
   ```
   pip install autogenstudio
   ```   

6. **Load the Anthropic API key into the environment (example api-key use your own)**:
   ```
   export ANTHROPIC_API_KEY="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"
   ```

7. **Start AutoGenStudio**:
   ```
   autogenstudio ui
   ```

8. **Start LiteLLM in a separate terminal (with conda activate claude-autogen)**:
   ```
   litellm --model claude-3-haiku-20240307
   ```

9. **Configure the new model in AutoGenStudio**:
   - Browse 127.0.0.1:8081 (can be different, depending on what is displayed in the terminal for AutoGen)
   - Go to "Build" > "Models" > "New Model"
   - Enter the following values:
     - Model: `claude-3-haiku-20240307`
     - API Key: `anything`
     - Base URL: `http://0.0.0.0:4000`
   - Save the configuration

After completing these steps, you have successfully set up Claude 3 Haiku in AutoGen 2 and can now use it now.
