# CodeBud
An intelligent coding companion that generates code from natural language prompts and then explains the generated code to the user in an easy-to-understand language. 
Additionally, it can also assist in debugging and code correction. 
## Project Status
In development - Module 3 in progress along with a few developments ongoing in module 1
## Modules
**Module 1:** Natural Language Understanding (NLU) Pipeline  
The NLU module is the entry point of CodeBud. Before any code can be generated, the system must first understand what the user is asking — this is Module 1's job.
Given a prompt like:
> "Write a Python function to find factorial"

The module extracts two things:  
* Intent — what the user wants to do (e.g. generate_code, debug_code, explain_code)  
* Slots — the parameters of that intent (e.g. language: Python, task: factorial function)  
This structured output is then passed downstream to the code generation engine.
> *Powered by BiLSTM-CRF trained on the SNIPS NLU dataset.*

*Module 1 achieves 97.64% intent classification accuracy on the SNIPS test set (1,400 samples, 7 intent classes).*  
  
**Module 2:** Code Generation Engine  
  Generates syntactically correct, multi-language code from structured intent and slot inputs extracted by the NLU module.  
  RAG pipeline along with external API key being used for code generation. RAG system retrieves relevant code/knowledge-base context and then uses the Groq LLM for generation.  
**Module 3:** Code Explanation  
  Explains generated code line by line in beginner-friendly language  
**Module 4:** Debugging Assistant  
  Works alongside user to point out errors being generated or in case a source code is given, fixes the errors and return a clean code.  
**Module 5:** Code Optimization  
  Recommends efficient alternatives to improve execution speed and reduce memory usage  
**Module 6:** Documentation Generator  
  Automatically produces inline comments, function descriptions, and README-ready API documentation  
**Module 7:** Learning Assistant  
  Explains programming concepts, provides examples, and recommends resources based on user queries  
**Module 8:** Code Review System  
  Analyzes code quality, flags code smells, checks naming conventions, and suggests refactoring opportunities  
