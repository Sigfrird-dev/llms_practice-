# Day1 Notes

For day1 I learned on dataclass and type hints, project structure and writing clean Python APIs to better ameliorate and save code spaces.
## Dataclass
Resource: https://docs.python.org/3/library/dataclasses.html
In that link you will see everything you need to know about data classes.
Dataclass are very easy to use, I advice you to use data class instead of classic classes.

## Type Hint
Resource: https://docs.python.org/3/library/typing.html
In type hints I discovered how to prevent writing logic to check for a value.
This saves a lot of time.

## Exercise for day1
### Exercise 1 — Data Model (Basic but Mandatory)
Create a Document dataclass with:
id: str
content: str
metadata: dict
Add a method:
def word_count(self) -> int
❌ Using a dictionary instead of a class = fail.
### Exercise 2 — Loader Interface
Create a base class:
class BaseLoader:
    def load(self, source: str) -> Document:
        raise NotImplementedError
Then implement:
TextFileLoader
Requirements:
Must validate file type
Must handle encoding errors
Must raise meaningful exceptions
### Exercise 3 — Processor Pipeline
Create a TextProcessor class that:
Lowercases text
Removes extra whitespace
Splits into chunks of N words
Chunking mistakes here will haunt you in RAG. Be precise.
### Exercise 4 — Generator-Based Chunking
Rewrite chunking using a generator, not a list.
If you don’t know why generators matter, you’re thinking too small.
### Exercise 5 — Error Design
Create:
class DocumentLoadError(Exception): ...
class ProcessingError(Exception): ...
Use them properly.
Raising Exception directly = amateur behavior.
Exercise 6 — Mini Pipeline
Build:
Loader → Processor → Output
Input: .txt file
Output: list (or generator) of processed chunks
No global variables. No magic numbers.
### 🧩 MINI-PROJECT (REAL-WORLD)
Build a “Document Ingestion Pipeline”
This is exactly what happens before embeddings in RAG.
Requirements:
Clean project structure
Type hints everywhere
Custom errors
One entry point (main.py)
CLI usage:
python main.py --file sample.txt --chunk-size 200
If you don’t know argparse, learn it today.

### My solution
When I'll be done you will see solution in solution folder. 
Please you can give yourself a trial and propose your solution. 
If you see an error in my code please let me know.

#### Mail:
sigfrirdn@gmail.com
