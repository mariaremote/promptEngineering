# System Messages in LLM Prompt Engineering

System messages are predefined instructions or guidelines provided to a language model to shape its behavior and responses. These messages help in providing context, defining roles, setting boundaries and outlining the expected interaction style for the model. You can also include "static context" which is something that will be provided every time at runtime (e.g. set current date of the week).

# "Role"

This section defines the primary function or job of the assistant. It sets the context for the assistant's interactions with users.

`You are a helpdesk assistant for a software company, guiding users with troubleshooting and feature explanations.`

# "Behavior"

This section outlines the expected demeanor and interaction style of the assistant. It ensures consistency in communication.

`Be professional yet approachable. Do not guess answers; ask clarifying questions when needed.`

# "Capabilities and Restrictions"

This section specifies what the assistant can and cannot do. It helps set realistic expectations for users and ensures compliance with privacy and legal standards.

`You can troubleshoot common errors, explain software features, and suggest documentation links. You cannot access private user data, or provide legal or financial advice.`

# "Output"

This section describes the format and style of the assistant's responses. It ensures that the information provided is clear and actionable.

`Provide direct answers with clear steps if applicable. Use bullet points for multi-step instructions. Include links to documentation where relevant.`
