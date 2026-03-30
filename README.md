# COMPX234 - Lab Assignment 2

## 1. Design Explanation
In this lab, I implemented a monitor to solve the Readers-Writers problem using Python. I used `threading.Condition` and `threading.Lock` to protect the shared state (`active_readers`, `active_writers`, and `waiting_writers`).

My logic is:
- Multiple readers can read at the same time if no one is writing.
- A writer needs exclusive access, so it must wait if there is any reader or another writer working.
- I used `while` loops for the `wait()` conditions. This ensures that when a thread wakes up, it re-checks the state to avoid race conditions.

## 2. How to Run
Open the terminal in this folder and run the python file:
`python readers_writers.py`

## 3. Sample Output
Reader 2 wants to read
Reader 2 starts reading. Active readers = 1
Reader 2 is READING
Reader 3 wants to read
Reader 3 starts reading. Active readers = 2
Reader 3 is READING
Writer 1 wants to write
Reader 1 wants to read
Reader 1 starts reading. Active readers = 3
Reader 1 is READING
Writer 2 wants to write
Reader 2 stops reading. Active readers = 2
Reader 2 finished reading
Reader 1 stops reading. Active readers = 1
Reader 1 finished reading
Reader 1 wants to read
Reader 1 starts reading. Active readers = 2
Reader 1 is READING
Reader 3 stops reading. Active readers = 1
Reader 3 finished reading
Reader 2 wants to read
Reader 2 starts reading. Active readers = 2
Reader 2 is READING
Reader 1 stops reading. Active readers = 1
Reader 1 finished reading
Reader 3 wants to read
Reader 3 starts reading. Active readers = 2
Reader 3 is READING
Reader 2 stops reading. Active readers = 1
Reader 2 finished reading
Reader 1 wants to read
Reader 1 starts reading. Active readers = 2
Reader 1 is READING
Reader 2 wants to read
Reader 2 starts reading. Active readers = 3
Reader 2 is READING
Reader 1 stops reading. Active readers = 2
Reader 1 finished reading
Reader 3 stops reading. Active readers = 1
Reader 3 finished reading
Reader 2 stops reading. Active readers = 0
Reader 2 finished reading
Writer 2 starts writing
Writer 2 is WRITING
Reader 3 wants to read
Writer 2 stops writing
Writer 2 finished writing
Reader 3 starts reading. Active readers = 1
Reader 3 is READING
Reader 3 stops reading. Active readers = 0
Reader 3 finished reading
Writer 1 starts writing
Writer 1 is WRITING
Writer 2 wants to write
Writer 1 stops writing
Writer 1 finished writing
Writer 2 starts writing
Writer 2 is WRITING
Writer 1 wants to write
Writer 2 stops writing
Writer 2 finished writing
Writer 1 starts writing
Writer 1 is WRITING
Writer 1 stops writing
Writer 1 finished writing
Simulation complete. All threads have finished.