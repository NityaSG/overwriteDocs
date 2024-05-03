# RAG Fusion

**Parallel Retrieval of Information from Two Data Sources (Original Document & Addendum):**
The retrieved information is compared, and the final information is updated and provided to the user accordingly.

## Technology Stack:
- **GPT-3.5 Turbo:** Used for retrieval purposes.
- **GPT-4:** Used for decision-making purposes.
- **Pinecone:** A vector database to store the information.
- **Langchain:** A framework to manage LLM solutions.
- **OpenAI text-embedding-3-large (3072 dimensions):** Used for embedding textual data.

## Procedure:
1. **Query the Vector Database:** Containing the chunks of original documents.
2. **Query the Vector Database:** Containing the chunks of addendum documents.
3. **Inject the Retrieved Responses:** Into a tuned prompt which will make judgments based on the two inputs.
4. **Decision-Making Prompt Model:** This model decides:
   - Whether the addendum retrieved information is relevant or not.
   - If yes, then alter the changes in the primary information.
   - If no, then return the original information.

## Reasons for This Approach:
1. **Divide a Bigger Task into Smaller Ones:** Helps in managing complexity.
2. **Introduce a Hard Boundary Between Addendums and the Original Document:** To avoid ambiguous responses.
3. **Awareness of Data Derivation:** Makes the LLM more capable of building accurate responses.
4. **Division of Vector Database:** Reduces the tokens consumed and the vectors retrieved from the vector database.
5. **Less Context in Each LLM:** Improves the LLM's performance in terms of accuracy.



original.txt contains the text about the original document. The OCR was done by gemini pro-vision experimental
