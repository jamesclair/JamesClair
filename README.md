# Senior Platform Software Engineer

[![trophy](https://github-profile-trophy.vercel.app/?username=ryo-ma&theme=onedark)](https://github.com/ryo-ma/github-profile-trophy)


# Projects

With a majority of my 16 years in enterprise security, software and engineering fields I can only share a small collection of my full portfolio due to most of the software and solutions being proprietary.  Below is a list of projects which were deemed fit for public consumption.

## LogRhythm

### [Axon](https://logrhythm.com/products/logrhythm-axon/)

A greenfield rewrite of LogRhythm's core data security analytics product as a highly scalable, highly available, multi-cloud/on-prem hybrid multi-tenant security intelligence and event management system.

In 2019 The VP of SE, one director, two architects and I (platform engineering lead) set out to rebuild Logrhythm's core SIEM as a cloud first platform.  For the next three years, following cloud native industry best practices, we began designing, building, testing, hiring, teaching and evangelizing the new platform while delivering on a very tight timeline.

Here are some of the industry principles, requirements, and best practices I learned, taught and we used to accomplish our goals:

<details><summary>Everything As Code</summary>
<ul>
 <li>Infrastructure, pipeline, services, configuration, environments and platform.  Why? For the single source of truth, visibility, collaboration, versioning, security and auditing that a central VCS can provide.  It forces you to introduce developer tools to non-developers, which is tough but worth it in the end because it lends well to collaborating in globally distributed work force.</li>  
<li>Atomic commits = atomic versions which enables intelligent service deployments (rollforward/rollback).</li>
<li> Most VCS systems include deep integrations for CI/CD tools, i.e github actions to build a full SDLC out of parallelizable, on-demand, asynchronous workflows for continuously building, testing, scanning, releasing, deploying and promoting services.  The chosen CI/CD tool should allow for custom runtime.</li>
</ul></details>

<details><summary>Business Logic and Services</summary><ul>
<li> The platform will combine both synchronous and asynchronous architectures with a preference given to asynchronous services that can be parallelized and stateless.  Stateless svcs are much cheaper as they can easily scale on-demand and because they have no state to track, store, or recover after an unexpected issue these services are easier and cheaper to manage.  For services that require state, the details of that state like how it is stored, retrieved, and processed should be abstracted away from any other entity outside of the service's namespace.  If another entity is dependent on knowledge derived from another service's state it should go through the services API.  Isolating access all stateful service's data to an audited API we can better enforce security policies, schemas and validations around how that information will be shared and referred to while keeping other REST clients unaware of the details of how the data or algorithms functioned internal to the service.</li>
<li> The chosen language must be widely used in enterprise computing</li>
</ul></details>
  
<details><summary>API First</summary><ul>
<li> The platform should be able to receive and respond quickly to very large, apikey and fluctuating volumes of data from remote connections.  As well as support concurrent, and geographically sparse connections from users of any externally exposed APIs and UIs.  Both types of connections should be scalable, load balanced, and deployable to MOST global regions.</li>
<li> Data sent should be stored and replicated to a distributed and highly available datastore.</li>
<li> The service should be highly available starting at three 99.9's and moving to four 99.99% uptime with monitoring.</li>
</ul></details>
  
<details><summary>Opensource First</summary><ul>
<li> # TODO: complete  section</li>
</ul></details>

> # Under Construction - Jim C - 1/17/23


# Scripts and Utilities
  
### Update all vault entries using another entry 

This script allows you to migrate from one path to another)
