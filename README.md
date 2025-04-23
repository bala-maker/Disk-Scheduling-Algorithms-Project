The Disk Scheduling Simulator allows users to explore and compare how different disk scheduling algorithms handle I/O requests. It simulates:

FCFS (First-Come, First-Served)
SSTF (Shortest Seek Time First)
SCAN (Elevator Algorithm)

For each algorithm, it computes:

The sequence in which disk requests are serviced
Total head movement (how far the disk arm moves)
Average seek time

📊 Why It Matters:
In operating systems, how disk I/O is scheduled can significantly affect performance. Choosing the right algorithm:

Reduces seek time
Improves response time
Balances fairness vs. efficiency

⚙️ Input Format
The program takes:

A list of disk track requests — integer values representing track numbers (e.g., 55 58 60 70 18)
Initial head position — starting location of the disk arm (e.g., 50)
Selected scheduling algorithm — "FCFS", "SSTF", or "SCAN"
Direction (for SCAN) — either "left" or "right"

🧠 Algorithm Descriptions
1. First-Come, First-Served (FCFS)
   
Services requests in the order they arrive.
Simple, fair.
Can lead to high head movement if requests are scattered.

Example:

Requests: [98, 183, 37, 122]
Head: 53
Sequence: [98, 183, 37, 122]

2. Shortest Seek Time First (SSTF)
   
Picks the request closest to current head.
Reduces seek time.
Can lead to starvation for far-away requests.

Example:


Requests: [98, 183, 37, 122]
Head: 53
Sequence: [37, 98, 122, 183]

3. SCAN (Elevator Algorithm)
   
Moves in a direction, servicing all requests until the end.
Then reverses direction.
Like an elevator: efficient and fair.

Example (Right direction):


Requests: [98, 183, 37, 122]
Head: 53
Sequence: [98, 122, 183, 199, 37] (assuming disk end = 199)

📤 Output Format

After execution, the program prints:
Order of service: The order in which requests are fulfilled
Total head movement: Sum of absolute movements of the disk head
Average seek time: total_head_movement / number_of_requests

🧱 Code Structure Overview

fcfs(requests, head)
Directly serves the requests in order.

Calculates total movement and average.

sstf(requests, head)
Iteratively selects the closest request to the current head.

Updates movement, sequence, and average.

scan(requests, head, direction, disk_size)`
Based on the direction, splits requests and services all in one pass.

Moves to end of disk if necessary, then reverses.
main()
Gets user input
Calls the chosen algorithm
Prints results

🧪 Sample Run

Enter disk track requests (space-separated): 98 183 37 122 14
Enter initial head position: 53
Choose algorithm (FCFS/SSTF/SCAN): SSTF

Order of service: [37, 14, 98, 122, 183]
Total head movement: 161
Average seek time: 32.2

💡 Enhancement Ideas

📈 Add matplotlib graphs for head movement over time.
💻 Build a GUI with Tkinter.
📁 Export results to .csv or .json.
🧪 Add unit tests to verify algorithm outputs.
📷 Visual screenshots for your GitHub README.
