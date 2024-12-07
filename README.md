# Railway Connection Solver

This project provides a solution for finding the best train connections between any two places using different cost functions. The implementation uses a dataset of Indian railway times and implements Dijkstra's algorithm for efficient pathfinding.

## Dependencies

### Programming Language

- **Python** (version 3.6 or above)

### External Libraries

- **pandas**: For data manipulation and CSV file handling.
- **networkx**: For creating and managing the graph representation of the train network.
- **heapq**: For implementing priority queues in Dijkstra's algorithm.
- **datetime**: For handling date and time operations.

### Installation

To install the required libraries, use the following command:

```bash
!pip install pandas networkx
```


## How to Run the Code

**1. Clone the Repository:** 

Clone the repository to your local machine.
```bash
git clone <repository-url>
cd <repository-directory>
```
**2. Prepare the Dataset:** 

Ensure the schedule.csv, mini-schedule.csv, and problems.csv files are in the root directory of the project.

**3. Run the Script:**

Execute the main script to solve the connection problems.

```bash
python main.py
```

The script will read the schedules and problems, compute the best connections based on the specified cost functions, and output the results to solutions.csv.

## Main Script
The main script follows these steps:

**1. Load Schedule Dataset:**

- Function: **load_schedule**
- Load the dataset, clean it, and format the columns properly.

**2. Create Directed Graph:**

- Function: **create_graph**
- Create a directed graph from the cleaned schedule data.
- Define a helper function within to add edges with travel time calculations.

**3. Cost Calculations:**

- Functions: **calculate_stops, calculate_travel_time, calculate_price, calculate_arrival_time**
- Calculate various metrics for paths (stops, travel time, price, arrival time).

**4. Load Problems Dataset:**

- Load the dataset containing the problems.

**5. Dijkstra's Algorithm:**

- Function: **dijkstra**
- Implement an adjusted Dijkstra's algorithm for different cost functions.
- Handle 'arrivaltime' cost function with special care for departure time.

**6. Format Connection:**

- Function: **format_connection**
- Format the output path into a readable connection string.

**7. Solve Problems:**

- Loop through each problem, load the corresponding schedule, create the graph, and find the best path using Dijkstra's algorithm.
- Store the solutions in a list.

**8. Save Solutions:**

- Convert the solutions list into a DataFrame and save it as a CSV file.


## Repository Structure
- **main.py:** The main script containing the logic for loading data, creating the graph, calculating costs, and finding the best connections.
- **schedule.csv:** The full train schedule dataset.
- **mini-schedule.csv:** A smaller subset of the train schedule for testing and debugging.
- **problems.csv:** The file containing the connection problems to be solved.
- **solutions.csv:** The output file containing the solutions to the problems.

## Cost Functions
- **Stops:** Minimize the number of stops.
- **Travel Time:** Minimize the total travel time in seconds.
- **Price:** Minimize the ticket price based on train tickets and stop tickets.
- **Arrival Time:** Minimize the time of arrival given a specific departure time.

## Example Connection Format
The connection format follows the pattern `Train No.:islno -> islno.` Consecutive segments of the same train are merged and separated by semicolons for different trains. For example: `56502 : 57 -> 58 ; 57305 : 69 -> 72.`

## Additional Information
**Time Management:** The code properly accounts for arrival and departure times that span multiple days.

**Change Time:** A minimum transfer time of 15 minutes is enforced when switching between trains. If the available transfer time is less than 15 minutes, the connection will be considered missed.

## Contact
My mail: zahra.amanli.za@gmail.com

My LinkedIn profile: www.linkedin.com/in/zahra-amanli 

