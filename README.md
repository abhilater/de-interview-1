# Build a pipeline to calculate Avg TTER metric

In the world of customer support we need to monitor agent performance to determine support quality. One of these metrics is <b>Time to each response</b>

<b>Time to each response</b> is the Avg time between the customer reply and agent response. In the case there are multiple customer replies before a agent response, you should consider the time between the first customer reply and the agent reply

## Input Events table

| Customer  | Action           | Agent  | Timestamp           | TicketId|
|-----------|------------------|--------|---------------------|----------|
| Hackshift | Issue Creation   |        | 2020-01-01 00:00:00 | 1        |
| Hackshift | Customer Reply   |        | 2020-01-01 00:00:00 | 1        |
| Hackshift | Agent Reply      | Agent1 | 2020-01-01 00:10:00 | 1        |
| Hackshift | Issue resolved   |        | 2020-01-01 00:10:00 | 1        |
| Hackshift | Issue Creation   |        | 2020-01-01 00:00:00 | 2        |
| Hackshift | Customer Reply   |        | 2020-01-01 00:00:00 | 2        |
| Hackshift | Agent Reply      | Agent2 | 2020-01-01 00:20:00 | 2        |
| Hackshift | Customer Reply   |        | 2020-01-01 00:25:00 | 2        |
| Hackshift | Customer Reply   |        | 2020-01-01 00:26:00 | 2        |
| Hackshift | Agent Reply      | Agent2 | 2020-01-01 00:30:00 | 2        |
| Hackshift | Issue resolved   |        | 2020-01-01 00:30:00 | 2        |

## Output Metrics table

| Customer | Agent | Date  | Average time to each response (minutes)|
|----------|-------|-------|----------------------------------------|
| Hackshift| Agent1|2020-01-01| 10.0|
| Hackshift| Agent2|2020-01-01| 12.5|


## Solution expectations
1. Solution should be functionally correct
2. Solution/Pipeline should scale for 1 TB events data volume daily
