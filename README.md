# Modelling_Queues_Healthcare
Modelling queues for a mental health hospital before and after my proposed change in strategy.
The notebook uses SimPy.
It models a queueing system where customers arrive, wait in line if needed, get served by one of several servers, and then depart.
Arrivals follow a Poisson process, meaning interarrival times are exponentially distributed with rate parameter λ (customers/hour). The base arrival rate λ can vary over time.
Normally, λ is constant but randomizes slightly each hour.
A lunch rush scenario multiplies λ by 4 between 12:00–14:00.
Service times are also exponentially distributed with mean 1/μ hours.
There are multiple servers (c servers), so the system is an M/M/c queue.
The performance metrics collected are:
Average wait time per customer, Average service time, Server utilization (fraction of busy time per server), Average number of customers in system, and Distribution of wait times (e.g., % of customers waiting under 5 minutes, 30 minutes, 1 hour, etc.).

The scenarios Tested are: 
Base case (λ, μ, c fixed), adding servers (capacity expansion), reducing service times (faster service), and with and without lunch rush surges.
Multiple runs are averaged for statistical stability.
The model is based on the M/M/c queue, where:
M = Markovian arrivals (Poisson, exponential interarrival times).
M = Markovian service times (exponential).
c = number of parallel servers
