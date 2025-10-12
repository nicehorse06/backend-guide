## 🐍 Python (for Backend Engineers)

### ⚙️ Language Core & Execution Model
- Decorator (function/class decorator)
- Context Manager (`with`, `__enter__`, `__exit__`)
- Generator & Iterator (`yield`, `yield from`)
- Comprehensions (list/dict/set)
- GIL (Global Interpreter Lock)
- Mutable vs Immutable
- Shallow Copy vs Deep Copy
- Variable Reference vs Assignment
- `is` vs `==`
- Exception Handling (`try/except/finally/raise`)
- Type Hinting / Annotations
- Pythonic Principles (EAFP vs LBYL)
- Function Call Mechanics (`*args`, `**kwargs`)
- Dataclass / NamedTuple / Enum
- Object Lifecycle (`__init__`, `__del__`)
- Garbage Collector / Reference Counting
- Dunder Methods (magic methods like `__str__`, `__repr__`, `__len__`)
- Any new Python3 feature

---

### 🧩 Concurrency & Parallelism
- Multithreading (`threading`, GIL impact)
- Multiprocessing (`multiprocessing`, `Process`, `Pool`)
- Asyncio (`async/await`, event loop, Task, Future)
- `concurrent.futures` (ThreadPoolExecutor, ProcessPoolExecutor)
- Thread safety / race condition
- I/O-bound vs CPU-bound distinction

---

### 🧠 Memory & Performance
- Memory management & object reuse
- Reference cycles & GC tuning
- `__slots__`
- Profiling tools: `timeit`, `cProfile`, `tracemalloc`
- Common performance traps (copying large lists, JSON serialization, etc.)

---

### 🧪 Testing & Debugging
- Unit testing basics (`pytest` / `unittest`)
- Mocking & Fixtures
- Debugging (`pdb`, `breakpoint()`)
- Logging (`logging` module)
- Exception stack trace analysis
- Code Quality / Linting: `flake8`, `black`, `isort`, `mypy`

---

### 🧰 Packaging & Environment
- Virtual environments (`venv`, `poetry`)
- Dependency management (`requirements.txt`, lock files)
- Project structure (src layout, `__init__.py`)
- `setup.py`, `pyproject.toml` basics
- Import system & module resolution
- Versioning / Semantic versioning
- Packaging tools (`build`, `twine`, `wheel`)

---

### 🧱 System & I/O
- File I/O (`open`, `pathlib`, `os`, `shutil`)
- subprocess / shell command execution
- Signal handling (`signal` module)
- Environment variables (`os.getenv`)
- Config management (`dotenv`, `pydantic-settings`)
- JSON / YAML parsing
- CLI design (`argparse`, `click`)

---

### 🌐 Networking & Backend Essentials
- Socket programming basics
- HTTP requests (`requests`, `httpx`)
- WSGI vs ASGI (conceptual)
- RESTful API fundamentals
- Serialization: JSON, Pickle
- Rate limiting / retry logic
- Connection pooling
- Caching (Redis / Memcached concepts)
- Logging & metrics (structured logging)

---

### 🧩 Asynchronous & Distributed Systems
- Celery / Task queues (concept + retry/schedule)
- Message brokers (Redis, RabbitMQ)
- Event-driven patterns
- asyncio + I/O libraries (aiohttp)
- Thread-safe shared state & Queue
- Multiprocessing shared memory

---

### Frameworks
- Django vs Flask
- Django ORM
    - Bulk import
- Middleware
- Sentry
- Celery