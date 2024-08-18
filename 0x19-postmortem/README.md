<h1>How did the API Gateway experience a complete outage?</h1>
<h2>Incident Summary</h2>
<p>Impact: The API Gateway, a core component of our microservices architecture, experienced a complete outage. This resulted in a major downtime for our web application, impacting approximately 80% of our user base. Users reported experiencing slow load times, error messages, and intermittent service availability.</p>
<img src="/Postmortem_project.png" alt="">
<h2>Root Cause:</h2>
<p>A combination of factors contributed to the outage. A misconfiguration of the API Gateway load balancer caused traffic to be distributed unevenly across the backend servers. This overload on certain servers led to resource exhaustion and eventual failure. Additionally, a recent code change introduced a bug that exacerbated the issue by increasing the load on the API Gateway.</p>
<h2>Timeline</h2>
<ul>
<li>11:00 AM UTC: The first reports of slow load times and error messages are starting to come in from users.</li>
<li>11:15 AM UTC: The monitoring system triggers alerts for high error rates and CPU usage on the API Gateway.</li>
<li>11:20 AM UTC: The engineer on duty begins investigating the issue, focusing on the API Gateway and its backend servers.</li>
<li>11:30 AM UTC: Initial analysis indicates a potential network issue, but further investigation reveals no network-related issues.</li>
<li>11:45 AM UTC: The incident is escalated to the engineering team lead, who assembles a team to address the issue.</li>
<li>12:00 PM UTC: The team identifies a misconfiguration in the load balancer as the root cause.</li>
<li>12:15 PM UTC: The load balancer configuration is corrected, redistributing traffic more evenly across the backend servers.</li>
<li>12:30 PM UTC: Services are restored, and the API Gateway is operating normally.</li>
</ul>
<h2>Root Cause and Resolution</h2>
<p>The root cause of the outage was a misconfiguration in the API Gateway load balancer that resulted in uneven traffic distribution. This overload on some of the backend servers led to resource exhaustion and failure. Additionally, a recent code change introduced a bug that increased the load on the API Gateway.</p>
<p>To resolve the issue, we as a team corrected the load balancer configuration to ensure that traffic was distributed fairly. We also identified and fixed the bug in the code.</p>
<img src="/figures-teamwork-brainstorming.jpg" alt="">
<h2>Corrective and Preventive Measures</h2>
<ul>
<li>Review and Improve Monitoring: Enhance the monitoring system to provide more detailed insights into API Gateway performance and identify potential issues early.</li>
<li>Enhance Change Management Processes: Implement more stringent change management procedures to reduce the risk of introducing bugs through code changes.</li>
<li>Conduct Regular Load Testing: Conduct regular load testing to identify potential bottlenecks and ensure that the API Gateway can handle the expected traffic.</li>
<li>Automate Incident Response: Automate the incident response workflow to speed up the process of detecting, diagnosing, and resolving issues.</li>
<li>Implement Circuit Breaker Pattern: Use Circuit Breaker Pattern to protect the API Gateway from cascading failures and isolate faulty services.</li>
<li>Increase Server Capacity: Consider increasing the capacity of your backend servers to handle future growth and prevent resource exhaustion.</li>
</ul>
