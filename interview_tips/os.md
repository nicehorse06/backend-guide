## 🖥️ Operating System (OS)

### 🧩 Process vs Thread vs Coroutine
- **Process**
  - Independent unit of execution with its own memory space.
  - Created via system calls (`fork`, `exec`).
  - Context switching between processes is **expensive** (full memory mapping).
  - Example: running two Python scripts simultaneously.

- **Thread**
  - Lightweight unit inside a process; shares memory and resources with other threads.
  - Context switching is faster than between processes.
  - Vulnerable to **race conditions** if accessing shared state.
  - Example: Python `threading.Thread`, Java `Thread`.

- **Coroutine**
  - Cooperative multitasking at user-space level.
  - No kernel involvement for scheduling → **extremely lightweight**.
  - Switches tasks at explicit yield points.
  - Ideal for I/O-bound concurrency.
  - Example:
    ```python
    async def fetch(): await io_task()
    ```
  - Frameworks: Python `asyncio`, Node.js event loop.

| Type | Managed By | Memory Space | Switching Cost | Use Case |
|------|-------------|---------------|----------------|-----------|
| Process | OS Kernel | Isolated | High | CPU-bound, Isolation |
| Thread | OS Kernel | Shared | Medium | Parallel computation |
| Coroutine | User space | Shared | Low | I/O-bound async tasks |

---

### ⚙️ Concurrency vs Parallelism
- **Concurrency** = managing multiple tasks at once (logical overlap).  
- **Parallelism** = running multiple tasks *simultaneously* on different CPU cores.  
- In single-core systems, concurrency ≠ parallelism.  
- Python example:
  - `asyncio` provides concurrency (I/O overlap).
  - `multiprocessing` enables true parallelism (bypasses GIL).

---

### ⚠️ Race Condition
- **Definition**
  - Occurs when two or more threads/processes access shared data simultaneously and the final result depends on the timing of their execution.
- **Example**
  ```python
  balance = 0
  def deposit(): 
      global balance
      tmp = balance
      tmp += 1
      balance = tmp
  ```
  Multiple threads calling `deposit()` → lost updates.
- **Detection**
  - Hard to reproduce (depends on scheduler timing).
  - Tools: Thread sanitizer, logging with timestamps.
- **Prevention**
  - Use synchronization mechanisms:
    - Mutex / Lock (`threading.Lock`)
    - Semaphore (limit concurrent access)
    - Monitor (combines lock + condition variable)
    - Atomic operations (CAS)
    - Thread-safe data structures
  - Follow **“shared-nothing”** design when possible.

---

### ⛓️ Deadlock
- **Definition**
  - A situation where two or more processes/threads are waiting indefinitely for each other to release resources.
- **Necessary Conditions** (Coffman’s 4 conditions)
  1. **Mutual Exclusion** – resource held exclusively.
  2. **Hold and Wait** – process holds one and waits for another.
  3. **No Preemption** – resource cannot be forcibly taken.
  4. **Circular Wait** – circular chain of resource dependencies.
- **Example**
  ```python
  lock1 = threading.Lock()
  lock2 = threading.Lock()

  def task1():
      with lock1:
          with lock2:  # waits forever if task2 holds lock2
              pass

  def task2():
      with lock2:
          with lock1:
              pass
  ```
- **Prevention Strategies**
  - **Resource Ordering**: acquire locks in consistent order.
  - **Timeouts**: use `lock.acquire(timeout=...)`.
  - **Deadlock Detection**: monitor dependency graph.
  - **Avoid Hold-and-Wait**: acquire all resources upfront.
  - **Use higher-level concurrency primitives** (thread pool, message queue).

---

### 🧠 Additional OS Concepts for Backend Engineers
- **Context Switching**
  - Overhead from switching CPU between tasks.
  - Optimize via fewer threads / async I/O.
- **Memory Management**
  - Stack (per thread), Heap (shared dynamic memory).
  - Leaks or unbounded caching → OOM errors.
- **Scheduling**
  - CPU scheduler decides which thread/process runs next.
  - Common algorithms: Round-Robin, Priority, Multilevel Queue.
- **Inter-Process Communication (IPC)**
  - Mechanisms: Pipes, Sockets, Shared Memory, Message Queues.
  - Example: FastAPI talking to Redis (separate process).
- **Signals**
  - OS interrupts for process control (`SIGINT`, `SIGTERM`).
  - Used for graceful shutdown or cleanup.
- **File Descriptors**
  - Everything in Unix is a file (socket, device, file).
  - FD leaks cause “Too many open files” errors.
- **System Calls**
  - Interface between user space and kernel (`read`, `write`, `fork`).
  - Monitor via `strace` or `dtruss`.
- **Page Cache**
  - OS buffers disk reads/writes for performance.
  - Important for database I/O and fsync operations.

---

### 🧩 Real-World Scenarios
- Web servers (Gunicorn, uWSGI, Nginx) use **multi-process** for CPU scaling.  
- Thread pools used for short-lived blocking tasks.  
- Async frameworks (FastAPI, Node.js) leverage **event loops** to handle massive I/O concurrency.  
- Containers and K8s pods are **process-level isolation**, not full virtualization.  
- Monitoring tools: `htop`, `top`, `ps`, `strace`, `lsof`.

---

### ⚡ Quick Summary
> **Processes** are isolated programs; **threads** share memory; **coroutines** enable lightweight concurrency.  
> **Race conditions** occur when threads modify shared state unsafely — fix via locks or atomic ops.  
> **Deadlocks** arise from circular lock dependencies — prevent by consistent lock ordering or timeouts.  
> Efficient backend systems balance concurrency and safety through design and controlled synchronization.
