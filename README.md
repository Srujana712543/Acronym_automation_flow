# Acronym_automation_flow
Automates acronym detection and definition from teams chats and channels so that the organization is always updated with all acronyms associated with their projects.

```mermaid
flowchart TD
    A[Start: Flow triggers when a new chat is added in Teams channel/chat/group chat] --> B[The compose action then combines the body of a new message preparing the content for further procession in the flow]
    B --> C[Initialize the body of the message to a variable]
    C --> D[Parse JSON then converts the content in the message into a structured format]
    D --> E[Get the existing items from the SharePoint List and check for specific conditions to create new items in the same SharePoint list if they do not already exist in a for-each loop- Regex expressions.]
    E --> F[In apply-to each, add a condition that checks for the existence of acronyms and if true, adds them to the list ]
    F --> G[In another apply-to each, it checks if the acronym is already in the list. If false, add the new acronym at the end]
    G --> H[End]
