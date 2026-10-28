# evals-in-ai-
The video outlines a framework for ensuring **AI reliability** in high-stakes environments like healthcare by combining **observability** and **evals**.

### Core Reliability Framework

*   **Observability:** This involves capturing "agent traces," which include system prompts, tool outputs, and the decision-making logic of an AI agent. By storing these interactions, engineers can debug system performance and understand how an agent reaches its conclusions.
*   **Evals:** Serving as the Quality Assurance (QA) for AI, evaluations are used to test specific components of an agent. Unlike traditional software unit tests, evals focus on the non-deterministic nature of LLMs, checking for issues like prompt leakage, privacy concerns, and logical errors in tool utilization.

### Key Metrics for Evaluation

To confirm an application is reliable, the speaker recommends measuring three primary indicators:

*   **Answer Relevancy:** Verifies that the AI's output is directly related to the user's specific query, ensuring it doesn't wander off-topic.
*   **Groundedness:** Checks if the AI's response is based strictly on the provided context (such as retrieved documents or tool data). This is the primary method for detecting and minimizing **hallucinations**.
*   **Tool Sequence Accuracy:** Monitors the order in which an agent calls tools. It ensures that the agent follows the correct logical workflow, such as gathering necessary user information before attempting to process a payment or performing a search.

### Implementation Best Practices

*   **Developer Ownership:** The responsibility for designing and executing evaluations should lie with the engineers building the system, rather than an isolated QA team.
*   **Data Strategy:** Because ground truth is often absent, engineers must curate high-quality datasets. This involves creating **synthetic datasets** or working closely with **subject matter experts** to establish a "golden dataset" for testing.
*   **Methodology:** Evaluation techniques involve comparing the user query, system instructions, model response, and context. While "accuracy" is a general goal, the speaker emphasizes using precise metrics like **precision and recall** when evaluating how well an agent uses its available tools.
