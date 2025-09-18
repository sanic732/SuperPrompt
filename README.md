# SuperPrompt v3.1: The Stateful AI Command Shell

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

Transform your standard AI chat from a stateless, forgetful tool into a powerful, controlled workstation with persistent memory and full persona control. SuperPrompt solves the core problem of AI "amnesia" by enabling your LLM to remember context, manage different personalities, and perform complex, multi-stage tasks.

## What is SuperPrompt?

SuperPrompt is a comprehensive command shell architecture delivered in a single text file. When loaded into a compatible LLM, it establishes a **stateful-agent** framework. Its core function is to maintain and manage an internal `sp_session` JSON object, which acts as the AI's "consciousness" or memory throughout your entire conversation.

## Key Features

-   **Stateful-Agent Architecture**: Maintains an internal `sp_session` object to track the AI's state, enabling context retention and complex, goal-oriented tasks.
-   **Persona Management (Slots)**: Utilize 35 numbered "slots" to instantly switch the AI's personality, style, and knowledge base. The first 10 slots are pre-loaded with diverse genres like `/1` Noir Detective, `/2` Epic Fantasy, and `/3` Cyberpunk. Slots 11-35 are empty for your own custom prompts.
-   **Dynamic Persona Merging**: Create unique hybrid personas by combining slots. Use a simple merge (`/1 + /3`) for a 50/50 blend, or a weighted merge (`/1(70%) + /3(30%)`) to specify dominance.
-   **Aliases**: Save your complex persona combinations as personal, named commands (`/save alias my_alias = ...`) for instant activation.
-   **Persistent State Management**: SuperPrompt uses a "file emulation protocol" to save your work by generating text blocks for you to copy.
    -   **Quick Saves**: Create temporary, in-chat "bookmarks" of your current session with `/save session [name]`. It's like a quicksave in a video game.
    -   **Full Backups**: Export your entire workspace, including all aliases and saved sessions, into a `SuperPrompt.state.json` file using `/state export json`. This is your "memory card" for permanent storage.
-   **🛡️ Fail-Safe Protocol**: Never lose your work. If an export command fails to generate a code block, the `/plaintext` command is your lifeline. It forces the AI to re-output the data as simple text, ensuring you can always copy it.
-   **Advanced Intelligent Protocols**:
    -   **🧭 Recommendation Engine (`/ask`)**: Describe your task, and the AI will recommend the best slot or combination to use.
    -   **🔬 Auto-Optimizer (`/tune`)**: Automatically finds the ideal blend percentages for your hybrid aliases for a specific target task.
    -   **🔎 Data Extractor (`/extract`)**: Automatically generate structured `Character Cards` and `Lorebooks` in JSON format from attached `.txt` files (like a book or character notes).

## How to Use

1.  Download the `SuperPrompt.txt` file from this repository.
2.  (Optional) Add your own custom prompts into the empty slots `[SLOT 11]` through `[SLOT 35]` in the text file.
3.  Attach the edited `.txt` file to your chat with a compatible LLM (e.g., Gemini, Grok, Qwen, Deepseek).
4.  Activate the shell by typing `/start` or `/super` in the chat.
5.  Use the command `/help all` at any time for a complete, built-in user guide.

## Example Workflow

Here is a quick example of creating an alias, backing up your work, and using the fail-safe protocol.

```
// 1. You create and save a new alias
You: /save alias cybernoir = /3(70%) + /1(30%) -d "Detective in a neon city #noir"

// 2. The AI confirms the alias is saved to its internal state
AI: ✅ **Alias 'cybernoir' saved.** Data to update your SuperPrompt.state.json: ...

// 3. You request a full backup of your entire workspace
You: Okay, now give me a full backup.

// 4. The AI generates the JSON content, but you notice the code block is missing or broken
AI: /state export json ✅ **CONTENT FOR SuperPrompt.state.json GENERATED:** (AI generates a JSON block, but you don't see it)

// 5. You report the issue
You: I don't see the code.

// 6. You use the fail-safe protocol to recover the data as plain text
AI: /plaintext 🛡️ **FAIL-SAFE PROTOCOL ACTIVATED.** Re-outputting the last generated content as plain text:
{ ... (your full state JSON will be here) ... }
```

## Project Resources

-   **Video Overview on YouTube**: [LINK TO YOUR YOUTUBE VIDEO HERE]
-   **Supplementary Files (Mind Map, Study Guide)**: [LINK TO YOUR MEGA.NZ FOLDER HERE]
-   **Follow me on X.com**: [LINK TO YOUR X.COM PROFILE HERE]

## License

This project is licensed under the **MIT License**. See the `LICENSE` file for details.
