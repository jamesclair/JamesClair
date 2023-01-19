
# Jim Clair - Senior Platform Software Engineer

[![trophy](https://github-profile-trophy.vercel.app/?username=ryo-ma&theme=onedark)](https://github.com/ryo-ma/github-profile-trophy)

# Projects

Below is a list of some of my most notable projects.  Some projects are proprietary and are therefore described using only with already publically available information.

<details><summary><href>
<a href="https://logrhythm.com/products/logrhythm-axon/">Axon</a></summary>


<blockquote>A proprietary greenfield rewrite of LogRhythm's core data security analytics product as a highly scalable, highly available, multi-cloud/on-prem hybrid multi-tenant security intelligence and event management system.</br> 

In 2019 two architects and I (the platform engineering lead) set out to rebuild Logrhythm's core SIEM as a cloud first platform.  For the next three years, following cloud native industry best practices, we began designing, building, testing, hiring, teaching and evangelizing the new platform while delivering on a very tight timeline.  The Axon platform went GA on Oct. 2022.</br></br>

**Design Principals**

  <blockquote>
  
  <details><summary>GitOps, CI/CD and Infrastructure As Code</summary>
  
  <ul>
   <li>Infrastructure, pipeline, services, configuration, environments and platform should all be code.  Why? For the single source of truth, visibility, collaboration, versioning, security and auditing that a central VCS can provide.  It forces you to introduce developer tools to non-developers, which is tough but worth it in the end because it lends well to collaborating in globally distributed work force.</li>  
  <li>Atomic commits = atomic versions which enables intelligent service deployments (rollforward/rollback).</li>
  <li> Most VCS systems include deep integrations for CI/CD tools, i.e github actions to build a full SDLC out of parallelizable, on-demand, asynchronous workflows for continuously building, testing, scanning, releasing, deploying and promoting services.  The chosen CI/CD tool should allow for custom runtime.</li>
  </ul>
  </details>
  
  <details><summary>Service Design</summary>
  <ul>
  <li> The platform will combine both synchronous and asynchronous architectures with a preference given to asynchronous services that can be parallelized and stateless.  Stateless svcs are much cheaper as they can easily scale on-demand and because they have no state to track, store, or recover after an unexpected issue these services are easier and cheaper to manage.  For services that require state, the details of that state like how it is stored, retrieved, and processed should be abstracted away from any other entity outside of the service's namespace.  If another entity is dependent on knowledge derived from another service's state it should go through the services API.  Isolating access all stateful service's data to an audited API we can better enforce security policies, schemas and validations around how that information will be shared and referred to while keeping other REST clients unaware of the details of how the data or algorithms functioned internal to the service.</li>
  <li> The chosen language must be widely used in enterprise computing</li>
  </ul>
  </details>
    
  <details><summary>API First</summary>
  <ul>
  <li> The platform should be able to receive and respond quickly to very large fluctuating volumes of data from remote connections.  As well as support concurrent, and geographically sparse connections from users of any externally exposed APIs and UIs.  Both types of connections should be scalable, load balanced, and deployable to MOST global regions.</li>
  <li> Data sent should be stored and replicated to a distributed and highly available datastore.</li>
  <li> The service should be highly available starting at three 99.9's and moving to four 99.99% uptime with monitoring.</li>
  <li> All connections must be encrypted, authenticated and authorized by an apikey or jwt</li>
  </ul>
  </details>
    
  <details><summary>Opensource First</summary>
   
   > :warning: **Section Under Construction - Jim C - 1/17/23**

  </details>

   <details><summary>Container First</summary>
   
   > :warning: **Section Under Construction - Jim C - 1/17/23**

   </details>

   <details><summary>DevSecOps</summary>
   
   > :warning: **Section Under Construction - Jim C - 1/17/23**

  </details>
  
  </blockquote>
  
**Notable Accomplishments**
  <details><summary>Terraform</summary>
    Building and Designing our AWS infrastructure's base layer was one my first big projects for Axon.  We chose Terraform because of our need to support multiple clouds and on-prem, the teams familiarity with the technology, and Pulumi/CDK solutions weren't very mature yet.  Drawing on past experience from the LRCloud project and recent research I proposed a reusable multi-layer modular design connected together by Terragrunt.    Example layers would be global, vpc, and subnet.  Terragrunt is excellent for reducing duplicate code following DRY principals and allowed us to more easily compose all of our modules and layers into a single command.  We authored many new modules and combined them with upstream opensource modules to create our AWS accounts, ELB, Route53, gateways, IAM, VPC, S3, ECR, and security groups.  All necessary components of infrastructure for laying down self-managed kubernetes clusters.  We then wired the Terraform layer to output to json so we could consume it and feed it into our kubernetes layer allowing for integration and decoupling.  Our Terraform layer for Axon was so successful we used and extended it to migrate the newly procured Mistnet product into LogRhythm's AWS footprint a year later.
  </details>

</blockquote>
</details>

<details><summary><href>
<a href="https://github.com/jamesclair/DeliveryPathFinder">DeliveryPathFinder</a></summary>

DeliveryPathFinder is a python application that I chose to build in for my Data Structures and Algorithms 2 course while attaining my B.S. in CS. This program provides a shortest path solution for delivering a truck load of packages given their distance from a hub distribution center in Utah. To solve this my algorithm of choice was implementing Dijkstra shortest path algorithm.  The intention of this project wasn't to build the cleanest most re-usable code, it was instead to solve a complex problem with dynamic programming and self-adjusting data structures in the most efficient way possible.  There were much easier projects to pick from, however I wanted to really challenge my ability to understand complex graph traversals and other advanced DSA concepts.  If I have time in the future I would love to refactor this project using the clean code and software design principals that I have gained since this project.  There is certainly room for more named functions, less nested loops, tests, logging, and more efficient lookups, but it was never originally intended to be a long-lived/maintained project.
</details>

<details><summary><href>
<a href="https://github.com/jamesclair/TeamScheduler">TeamScheduler</a></summary>
TeamScheduler is a Java application I created for my B.S. in Computer Science. The project was meant to demonstrate competency in object oriented patterns, lambda functional programming, SQL/JDBC integration, encapsulation, abstraction, exception handling, APIs, Internationalization/Localization, Java and JavaFX.  This project implements a combination of the MVC, DAO, factory, and singleton software design patterns.

TeamScheduler is an extendable application that a global service team could use for scheduling, tracking and reporting of customer appointments.
</details>

<details><summary><href>
<a href="https://github.com/jamesclair/CareerAdvisorBot">CareerAdvisorBot</a></summary>

> :warning: **Section Under Construction - Jim C - 1/17/23**

</details>

<details><summary><href>
<a href="https://github.com/jamesclair/InventorySystem">InventorySystem</a></summary>
InventorySystem was a java app I built while learning JavaFX and MVC patterns.  (*It was the precursor to TeamScheduler project above.*)

</details>

<details><summary>Data Structures and Algorithms</summary>

- [AlmostIncreasingSequenceAlgorithm](https://github.com/jamesclair/AlmostIncreasingSequenceAlgorithm)
- [unlivable_rooms_algorithm](https://github.com/jamesclair/unlivable_rooms_algorithm)
- [find_longest_strings_algorithm](https://github.com/jamesclair/find_longest_strings_algorithm)
- [common_letter_counter_algorithm](https://github.com/jamesclair/common_letter_counter_algorithm)
- [integer_halves_sum_comparer](https://github.com/jamesclair/integer_halves_sum_comparer)
</details>

<details><summary><a href="https://github.com/jamesclair/user_store">REST Security in Spring Boot</a></summary>

> :warning: **Section Under Construction - Jim C - 1/17/23**

</details>

<details><summary>LRCloud</summary>

> :warning: **Section Under Construction - Jim C - 1/19/23**
</details>

<details><summary>Mistnet</summary>

> :warning: **Section Under Construction - Jim C - 1/19/23**
</details>

<details><summary>AIE Cross Correlation</summary>

> :warning: **Section Under Construction - Jim C - 1/19/23**
</details>

<details><summary>Early Access Program</summary>

> :warning: **Section Under Construction - Jim C - 1/19/23**
</details>

<details><summary>Release Champion Program</summary>

> :warning: **Section Under Construction - Jim C - 1/19/23**
</details>

<details><summary>Mayo Clinic</summary>

> :warning: **Section Under Construction - Jim C - 1/19/23**
</details>
