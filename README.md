
# Jim Clair - Senior Platform Software Engineer

[![trophy](https://github-profile-trophy.vercel.app/?username=ryo-ma&theme=onedark)](https://github.com/ryo-ma/github-profile-trophy)

# Projects

Below is a list of some of my most notable projects.  Some projects are proprietary and are therefore described using only already publically available information.

<details><summary><href>
<a href="https://logrhythm.com/products/logrhythm-axon/">Axon</a></summary>


<blockquote>A proprietary greenfield rewrite of LogRhythm's core data security analytics product as a highly scalable, highly available, multi-cloud/on-prem hybrid multi-tenant security intelligence and event management system.</br> 

In 2019 two architects and I (the platform engineering lead) set out to rebuild Logrhythm's core SIEM as a cloud-first platform.  For the next three years, following cloud native industry best practices, we began designing, building, testing, hiring, teaching, and evangelizing the new platform while delivering on a very tight timeline.  The Axon platform went GA in Oct. 2022.</br>

I was responsible for the creation of an enterprise platform as well as hiring and leading a Team of Senior-level engineers.  By the time I left, we had a team of 6 engineers, a PO, and a manager.  And another team of 7 SRE engineers that we were tasked with onboarding, training, and mentoring.</br>

<details><summary><b>Design Principals</b></summary><blockquote>
  
  <details><summary>GitOps, CI/CD and Infrastructure As Code</summary>
  
  <ul>
   <li>Infrastructure, pipeline, services, configuration, environments, and platform should all be coded.  Why? For the single source of truth, visibility, collaboration, versioning, security, and auditing that a central VCS can provide.  It forces you to introduce developer tools to non-developers, which is tough but worth it in the end because it lends well to collaborating in a globally distributed workforce.</li>  
  <li>Atomic commits = atomic versions that enable intelligent service deployments (roll forward/rollback).</li>
  <li> Most VCS systems include deep integrations for CI/CD tools, i.e. GitHub actions to build a full SDLC out of parallelizable, on-demand, asynchronous workflows for continuously building, testing, scanning, releasing, deploying, and promoting services.  The chosen CI/CD tool should allow for custom runtime.</li>
  </ul>
  </details>
  
  <details><summary>Service Design</summary>
  <ul>
  <li> The platform will combine both synchronous and asynchronous architectures with a preference given to asynchronous services that can be parallelized and stateless.  Stateless SVCs are much cheaper as they can easily scale on-demand and because they have no state to track, store, or recover after an unexpected issue these services are easier and cheaper to manage.  For services that require a state, the details of that state like how it is stored, retrieved, and processed should be abstracted away from any other entity outside of the service's namespace.  If another entity is dependent on knowledge derived from another service's state it should go through the services API.  By isolating access to all stateful service data to an audited API we can better enforce security policies, schemas, and validations around how that information will be shared and referred to while keeping other REST clients unaware of the details of how the data or algorithms function internal to the service.</li>
  <li> The chosen language must be widely used in enterprise computing</li>
  </ul>
  </details>
    
  <details><summary>API First</summary>
  <ul>
  <li> The platform should be able to receive and respond quickly to very large fluctuating volumes of data from remote connections.  As well as support concurrent, and geographically sparse connections from users of any externally exposed APIs and UIs.  Both types of connections should be scalable, load-balanced, and deployable to MOST global regions.</li>
  <li> Data sent should be stored and replicated to a distributed and highly available datastore.</li>
  <li> The service should be highly available starting at three 99.9's and moving to four 99.99% uptime with monitoring.</li>
  <li> All connections must be encrypted, authenticated, and authorized by an API key or jwt</li>
  </ul>
  </details>
    
  <details><summary>Opensource First</summary>
   
   > :warning: **Section Under Construction - Jim C - 1/22/23**

  </details>

   <details><summary>Container First</summary>
   
   > :warning: **Section Under Construction - Jim C - 1/22/23**

   </details>

   <details><summary>DevSecOps</summary>
   
   > :warning: **Section Under Construction - Jim C - 1/22/23**

  </details>
  
  </blockquote>
  </details>

  <details><summary><b>Contributions</b></summary>
  <blockquote>
  <details><summary>Terraform</summary>
    Building and Designing our AWS infrastructure's base layer was one of my first big projects for Axon.  We chose Terraform because of our need to support multiple clouds and on-prem, the team's familiarity with the technology, and the Pulumi/CDK solutions weren't very mature yet.  Drawing on experience from the LRCloud project and recent research I proposed a reusable multi-layer modular design connected by Terragrunt.    Example layers would be global, vpc, and subnet.  Terragrunt is excellent for reducing duplicate code following DRY principals and allows us to easily compose all of our modules and layers into a single command.  We authored many new modules and combined them with upstream open-source modules to create our AWS accounts, ELB, Route53, gateways, IAM, VPC, S3, ECR, and security groups.  All necessary components of infrastructure for laying down self-managed Kubernetes clusters.  We then wired the Terraform layer to output to JSON so we could consume it and feed it into our Kubernetes layer allowing for integration and decoupling.  Our Terraform layer for Axon was so successful we used and extended it to migrate the newly procured Mistnet product into LogRhythm's AWS footprint a year later.
  </details>
  <details><summary>AWS  Footprint</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
  
  <details><summary>IDP Integration (AWS, Okta, Keycloak, and Pomerium)</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
    
  <details><summary>Vault Operator</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
    
  <details><summary>Github Actions and CICD pipeline</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
    
  <details><summary>Auto Promotions</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
    
  <details><summary>Localdev Provisioning</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>

  <details><summary>Microservice Operator (Ansible)</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
    
  <details><summary>S3 Integration</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
    
  <details><summary>Firechief Program</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
    
  <details><summary>Kops CICD</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
    
   <details><summary>Opensearch Operator (Golang)</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>

  <details><summary>Sonarqube Scans</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>
 
  <details><summary>Flink Operator(s)</summary>
  
  > :warning: **Section Under Construction - Jim C - 1/22/23**
  </details>

  </blockquote>
</blockquote>
</details>

<details><summary><href>
<a href="https://github.com/jamesclair/DeliveryPathFinder">DeliveryPathFinder</a></summary>

DeliveryPathFinder is a Python application that I chose to build for my Data Structures and Algorithms 2 course while attaining my B.S. in CS. This program provides a shortest-path solution for delivering a truckload of packages given their distance from a hub distribution center in Utah. To solve this my algorithm of choice was implementing Dijkstra shortest path algorithm.  The intention of this project wasn't to build the cleanest most reusable code, it was instead to solve a complex problem with dynamic programming and self-adjusting data structures in the most efficient way possible.  There were much easier projects to pick from, however, I wanted to challenge my ability to understand complex graph traversals and other advanced DSA concepts.  If I have time in the future I would love to refactor this project using the clean code and software design principles that I have gained since this project.  There is certainly room for more named functions, fewer nested loops, tests, logging, and more efficient lookups, but it was never originally intended to be a long-lived/maintained project.
</details>

<details><summary><href>
<a href="https://github.com/jamesclair/TeamScheduler">TeamScheduler</a></summary>
TeamScheduler is a Java application I created for my B.S. in Computer Science. The project was meant to demonstrate competency in object-oriented patterns, lambda functional programming, SQL/JDBC integration, encapsulation, abstraction, exception handling, APIs, Internationalization/Localization, Java, and JavaFX.  This project implements a combination of the MVC, DAO, factory, and singleton software design patterns.

TeamScheduler is an extendable application that a global service team could use for scheduling, tracking, and reporting customer appointments.
</details>

<details><summary><href>
<a href="https://github.com/jamesclair/CareerAdvisorBot">CareerAdvisorBot</a></summary>

> :warning: **Section Under Construction - Jim C - 1/22/23**

</details>

<details><summary><href>
<a href="https://github.com/jamesclair/InventorySystem">InventorySystem</a></summary>
InventorySystem was a Java app I built while learning JavaFX and MVC patterns.  (*It was the precursor to the TeamScheduler project above.*)

</details>

<details><summary>Data Structures and Algorithms</summary>

- [AlmostIncreasingSequenceAlgorithm](https://github.com/jamesclair/AlmostIncreasingSequenceAlgorithm)
- [unlivable_rooms_algorithm](https://github.com/jamesclair/unlivable_rooms_algorithm)
- [find_longest_strings_algorithm](https://github.com/jamesclair/find_longest_strings_algorithm)
- [common_letter_counter_algorithm](https://github.com/jamesclair/common_letter_counter_algorithm)
- [integer_halves_sum_comparer](https://github.com/jamesclair/integer_halves_sum_comparer)
</details>

<details><summary><a href="https://github.com/jamesclair/user_store">REST Security in Spring Boot</a></summary>

> :warning: **Section Under Construction - Jim C - 1/22/23**

</details>
  
<details><summary>Mistnet</summary>

> :warning: **Section Under Construction - Jim C - 1/22/23**
</details>
  
  

<details><summary>LRCloud</summary>
As our platform manager quickly became our toughest bottleneck with events, alarms, and metadata datastore volumes began to climb, and repartitioning and maintenance jobs were unable to finish.  As a result, queries slowed, indexing slowed, and retention decreased.  Unfortunately, Engineering was unable to find a cost-effective or viable path for migrating away from Microsoft SQL for the PM because it held too much of our business logic in stored procedures.  This would make it very difficult to replace the datastore without having to recreate or migrate all of that logic with it.  

> :warning: **Section Under Construction - Jim C - 1/22/23**
</details>

<details><summary>CloudAI Service Launch</summary>

> :warning: **Section Under Construction - Jim C - 1/22/23**
</details>
  
<details><summary>Early Access Program</summary>

> :warning: **Section Under Construction - Jim C - 1/22/23**
</details>

<details><summary>Release Champion Program and Increased Release Cadence</summary>

At this point, my reputation for solving large complex issues was getting noticed and after speaking with the Co-Founder of LogRhythm Chris Peterson about the state of our releases and the future of DevOps, he asked me to become the new Global Technical Release Manager for LogRhythm.  This role was a hands-on technical role that would be focused on providing early feedback, and product expertise, re-building our early access program, and standardizing your agile release processes across the entire company.  The first big project my Partner Crystal Gregory and I worked on was the Release Champion program.  This was a volunteer-based program in which engineers PS, Sales, and Support would choose to champion an area of the product that aligned with an engineering team/product area.  Crystal or I would host a meeting between the champions and the engineering teams each sprint and new features, bugs, questions, and news would be discussed, planned, and documented.  According to our datasets, we more than tripled our internal content contributions, improved inter-org relationships, and chopped our Release Cycle down from almost a year to 6 months just by improving the way that we worked together.
</details>
  
<details><summary>AIE Cross Correlation Design, Best Practices Guide and 100k MPS</summary>

While we had bought ourselves time with the ES migration, this was only the beginning though as our largest Advanced Intelligence Engine, an LR-patented near-realtime streaming analytics service was only rated for 75k and its job was to correlate logs from one device with a log from any other device on the network and determine if it was suspicious behavior or violated security policies.  While the AIE was an amazing feat of data science and engineering it had one major problem it was never designed to horizontally scale.  The next year, I worked to optimize our largest clients and come up with the AIE cross-correlation design best practices, which gave customers a process by which they could over time create natural groups of log streams to be sent to dedicated AIEs to meet specific use cases.  This was achievable by finding a non-documented feature in the code that allowed you to filter which data went to which AIE based on the rules it hosted and the types of log data needed to satisfy it.  Overtime use cases that required similar log mixes could be grouped and sent to a single AIE.  This led to better filtering and more efficient workloads allowing us to achieve over 100k per AIE as well as simplify data routing for customers with thousands of rules and use cases.

</details>
  
<details><summary>LogRhythm and Splunk Integration Guide and Training</summary>

> :warning: **Section Under Construction - Jim C - 1/22/23**
</details>
  


<details><summary>Scaling to 100k, 200k, and 300k MPS and Elasticsearch Migrations</summary>

I led a team of enterprise engineers that helped LogRhythm's largest customers like Mayo Clinic and Cargill design and build out huge Security Operations Centers centered around the LogRhythm SIEM.  Our team helped save several accounts that were struggling due to the original product's ability to scale beyond a certain point.  First issue, we were on Microsoft SQL for both our log manager and platform manager data stores, which was switching to a per-core license model significantly impacting our margins.  Our Log Manager databases were the first bottleneck where large and complex queries were becoming too slow and we were exhausting our workarounds.  After our team convinced the business that to scale to the needed volume and still have a valuable product we needed more durability, horizontal scaling, read throughput, load balancing, and a potentially more time-series-friendly datastore.  Soon after the business chose Elasticsearch, where we spent the next 2 years re-architecting, expanding, and migrating all customers to using Elasticsearch.  This leads our customers to be able to break Logrhythm's barrier of 100k, 200k, and 300k Messages Per Second processing, and 110k indexing.

</details>
  
<details><summary>Best Practices Alarm and Response Runbook Database</summary>

After 8 months as a SIEM engineer, I developed a good reputation with folks at LogRhythm and they negotiated my transfer and moved me to Colorado to become a Senior Enterprise Consultant and Team Lead.  One of the biggest problems the Professional Services team was facing at the time was knowledge of how to use the product to serve their use cases, especially for the recent influx of new LARGE enterprise deployments.  These customers were building huge globally distributed 24/7 Security Operations Centers around the LogRhythm product, but many of them had never used it.  I chose to tackle this by creating a database of best practices where common steps could be re-used to build out runbooks of Best Practices for what to do when you receive a diagnostic alarm.  The database and form input were chosen to make it easy to input data and to make more modules as well, some of the results of this work can be seen today here: https://docs.logrhythm.com/docs/kb/additional-modules/logrhythm-diagnostic-module-user-guide
</details>
  
<details><summary>Fishnet Security Inc (Optiv), Cyber Security Bootcamp, and CISSP</summary>
  
After an honorable discharge, I started working at Fishnet Security (Now known as Optiv) as an Escalations Engineer to help enterprise customers manage and maintain their perimeter security systems, like firewalls, proxies, VPNs, routers, and load balancers.   I also attended night school at this time where I earned certifications in Microsoft, Cisco, CompTIA, Palo Alto, Checkpoint, Bluecoat, and Juniper.  After six years in the industry, I was able to attain my CISSP and  was asked to join the SIEM team where I helped deploy, update, and manage LogRhythm, HP ArcSight, and IBM Qradar products.  This required lots of log management, data analysis, security best practices, and large system solution engineering.
  
</details>  

<details><summary>Marines Tactical Data Systems Administrator</summary>

I started as a Systems Administrator in the Marines, where I gained a foundation for deploying, managing, and updating enterprise IT stacks.  Lots of Unix/Windows Server, Access, Networking, Security, and Database Administration.  I was billeted as the ops manager, received Top of my Class, a meritorious promotion, and 2 Col coins for large-scale service pack rollouts.
  
</details>
