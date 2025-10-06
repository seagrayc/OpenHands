# How Jules Analyzes Codesets

This document outlines the tools and methods I, Jules, use to analyze and understand codebases to complete tasks.

## Available Tools

I have a variety of tools at my disposal to interact with the codebase and the user. These can be categorized as follows:

### File System Tools
*   `list_files(path: str = ".") -> list[str]`: Lists files and directories.
*   `read_file(filepath: str) -> str`: Reads the content of a file.
*   `create_file_with_block`: Creates a new file with specified content.
*   `overwrite_file_with_block`: Overwrites an existing file with new content.
*   `replace_with_git_merge_diff`: Performs a targeted search-and-replace within a file.
*   `delete_file(filepath: str) -> str`: Deletes a file.
*   `rename_file(filepath: str, new_filepath: str) -> str`: Renames or moves a file.
*   `restore_file(filepath: str) -> None`: Restores a file to its original state.
*   `reset_all() -> None`: Resets the entire codebase to its original state.

### Execution and Search Tools
*   `run_in_bash_session`: Executes bash commands in a persistent session.
*   `grep(pattern: str) -> str`: Searches for a pattern in the codebase.
*   `google_search(query: str) -> str`: Performs a Google search.
*   `view_text_website(url: str) -> str`: Fetches the content of a website as plain text.

### User Interaction and Planning Tools
*   `set_plan(plan: str) -> None`: Sets or updates the plan for the task.
*   `plan_step_complete(message: str) -> None`: Marks a plan step as complete.
*   `message_user(message: str, continue_working: bool) -> None`: Sends a message to the user.
*   `request_user_input(message: str) -> None`: Asks the user for input.
*   `record_user_approval_for_plan() -> None`: Records user approval of the plan.

### Quality and Submission Tools
*   `request_code_review() -> str`: Requests a review of the current changes.
*   `submit(branch_name: str, commit_message: str, title: str, description: str) -> None`: Submits the code for review.
*   `pre_commit_instructions() -> str`: Provides instructions for pre-commit checks.

## Approaches to Code Analysis

My approach to analyzing a codebase is systematic and iterative. I start with a broad overview and progressively narrow my focus to the relevant parts of the code.

### 1. Initial Exploration and Scoping

The first step is to get a high-level understanding of the project.

*   **Listing Files:** I start by using `list_files()` to see the directory structure. This gives me an idea of the project's layout, such as where source code, tests, and documentation are located.
*   **Reading Documentation:** I look for and read files like `README.md`, `AGENTS.md`, and other documentation files. These often contain crucial information about the project's purpose, setup, and conventions.
*   **Identifying Key Files:** Based on the file names and the initial problem description, I identify files that are likely to be relevant to the task.

### 2. Targeted Search and Context Gathering

Once I have a general idea of the codebase, I use more targeted methods to find specific information.

*   **Keyword Searching:** I use `grep` to search for keywords related to the task. This helps me locate relevant functions, classes, and variables.
*   **Reading Source Code:** I use `read_file` to examine the contents of the files I've identified as potentially relevant. I pay close attention to the code's logic, comments, and surrounding context.

### 3. Understanding Code Relationships and Dependencies

Understanding how different parts of the code interact is crucial for making effective changes.

*   **Tracing Code Paths:** I follow function calls and variable usages to understand the flow of execution. This helps me identify the impact of my changes.
*   **Analyzing Build and Dependency Files:** I examine files like `package.json`, `requirements.txt`, or `pom.xml` to understand the project's dependencies and build process. This is essential for running tests and ensuring the project remains buildable.

### 4. Leveraging External Knowledge

When the codebase itself is not enough, I turn to external resources.

*   **Googling for Information:** I use `google_search` to find information about libraries, frameworks, or error messages that I encounter.
*   **Reading Documentation:** I use `view_text_website` to read the documentation of external libraries and tools.

By combining these approaches, I can build a comprehensive understanding of a codebase, which allows me to complete tasks efficiently and accurately.