IMPORTANT: This project does not officially represent the Pineapple Chatbox project in any capacity. This project is using it as a template as we test our expertise in various tools including: GitHub, Docker, Jira, TestRail, and LaTeX, for CS 3338: Software Engineer Tools, a class in Cal State LA.

Jira Link (MEANT FOR INSTRUCTOR):https://calstatela-cs3338-fall-team20.atlassian.net/jira/software/projects/PCS/boards/166

The system processes user queries through a natural language understanding pipeline powered by the spaCy machine learning library. When a user submits a question, the text is first analyzed to identify named entities and semantic intent. For example, in the query “What is Randy’s email?”, spaCy correctly recognizes “Randy” as an entity of type PERSON.

After entity recognition, the system determines the user’s intent, which in this case is to retrieve contact information. A statistical ranking model is then applied to score a collection of relevant source links using the extracted entity and intent information. The highest-ranked result is selected, and the corresponding email is retrieved and returned to the user as the final response.

In cases where a clear entity is not present — such as in the query “How do I apply for financial aid?” — the system activates a secondary Bayesian classification model. Common stop words (e.g., “I,” “do,” “for”) are first removed to isolate the core keywords of the query. These keywords are then compared across multiple predefined content categories, such as financial aid, computer science, and academic advising.

The most probable category is assigned a weighted accuracy boost and passed to the statistical ranking model for final evaluation. Since such queries often span broader informational domains, the system responds by providing the user with the most relevant webpage link rather than a short text-based answer.
