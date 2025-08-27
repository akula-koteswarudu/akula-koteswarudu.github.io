# My Journey at a MarTech Company: From Curious Intern to Full-Stack Engineer

*A story of growth, challenges, and building systems that handle millions of notifications*

---

## The Beginning: Stepping Into the Unknown

When I walked into the company in January 2023 as an intern, I had no idea I was about to embark on one of the most transformative experiences of my career. Like most interns, I started with the basics – watching YouTube videos about Spring Boot, building demo projects, and trying to understand what this company actually did.

But curiosity has always been my driving force. Instead of just completing assigned tutorials, I found myself diving deep into the Android SDK codebase that powers push notifications for millions of users. As I traced through functions that handled app lifecycle events and notification delivery tracking, something clicked. This wasn't just code – this was the invisible infrastructure keeping users connected to the apps they love.

Those early days of code exploration led to my first real contribution. While reading through the SDK, I started noticing bugs – small inconsistencies that others had missed. Each bug I reported felt like solving a puzzle, and my manager began to notice my attention to detail. Soon, I wasn't just reading code; I was understanding the entire ecosystem – from Google Services configurations to FCM backends, from testing on PCloudy devices to crafting perfect Postman requests for push notifications.

## The First Real Challenge: When Background Services Met New Android APIs

My first major project arrived sooner than expected. Android was updating its API requirements, and our legacy background services needed to migrate to WorkManager. I saw it as an opportunity to leave my mark on something real – something that would actually run in production and serve real users.

The migration wasn't just about changing APIs; it required understanding the fundamental differences in how Android handles background processing. I spent days reading documentation, testing different approaches, and ensuring backward compatibility. When the SDK finally shipped with my changes, I felt something I'd never experienced before – the pride of knowing that somewhere in the world, users were receiving notifications because of code I had written.

But the journey didn't stop there. The Android changes needed to propagate to our React Native SDK too. Suddenly, I was learning cross-platform development, understanding how native modules bridge to JavaScript, and managing release processes across multiple platforms. Each release taught me something new about the intricate dance between different technologies.

## The Experiment That Sparked Innovation

Around this time, my manager approached me with an experimental idea – what if we could build a system where the SDK itself could pull notifications that FCM failed to deliver? It was ambitious, requiring changes to both the SDK and backend infrastructure. Since the backend wasn't ready, we built a dummy API that returned the same notifications repeatedly. It seemed simple, but it was laying the groundwork for something much bigger.

Working directly with my manager on this experiment taught me about the importance of proof-of-concepts and iterative development. We weren't just building features; we were exploring possibilities and pushing the boundaries of what mobile notification systems could do.

## Trial by Fire: The On-Call Experience That Changed Everything

Then came the moment that would define my internship – and arguably my entire career trajectory. I became the first intern in company history to join the on-call rotation. My manager believed in me enough to let me experiment with whether interns could learn from the intense, real-world pressure of production support.

Those first few weeks were brutal. I was thrown into the deep end of systems I barely understood – CDP flows, MA backend processes, and complex client integrations that I'd only heard about in passing. Every ticket felt like a mountain to climb. I'd spend hours reading through codebases, tracing execution paths, and trying to understand how data flowed through our systems.

The senior engineers were helpful when they could be, but they had their own fires to fight. So I developed a different approach – I would dive into the code directly, reading entire applications from top to bottom until I understood not just what they did, but why they did it that way. This self-directed learning approach became my superpower.

Week after week, I was primary on-call with barely any breaks. It was exhausting, but it was also exhilarating. Each resolved incident taught me something new about system behavior, about how to read logs effectively, about the difference between temporary fixes and root cause solutions. I was developing an intuition for troubleshooting that would serve me for years to come.

By the end of my internship, I had accidentally become one of the most knowledgeable people about the company's core backend flows – knowledge that typically took engineers months to acquire.

## Beyond Code: Infrastructure and Optimization

Between incidents, I found myself working on infrastructure improvements alongside our principal engineer. Our AWS setup had evolved organically, with separate load balancers for different applications – but since our traffic wasn't that high, separate load balancers were unnecessary and costly. The principal engineer identified this inefficiency and guided me through implementing a consolidation strategy, moving to single load balancers with intelligent routing rules for both production and staging environments, significantly reducing our infrastructure costs.

I also worked with him to set up proper monitoring for several production applications that lacked visibility. Together, we implemented Monit and Node Exporters across these systems, dramatically improving our ability to monitor application health. These weren't glamorous tasks, but they were the kind of foundational work that prevents 3 AM outages.

## Transition to Full-Time: Entering the Banking Client Universe

When my internship ended and I transitioned to a full-time SDE role, I thought I understood what I was getting into. I was wrong. The banking client stack was a completely different beast – simpler in some ways, but carrying the weight of being one of our most critical clients. This was a bank's critical infrastructure, and there was no room for error.

The banking client's world revolved around two fundamental flows: promotional campaigns that arrived as batch files via SFTP, and real-time transactional notifications that came through socket connections. Each flow had its own personality, its own challenges, and its own requirements for reliability and security.

The promotional flow felt like watching a well-orchestrated machine. Files would arrive on our SFTP server, get picked up by cron jobs, transferred to processing VMs where Flume applications would transform and validate the data before feeding it into Kafka. It was batch processing at scale, requiring careful attention to error handling and data integrity.

The transactional flow was the complete opposite – real-time, high-stakes, and demanding instant responses. Notifications would arrive through our Node.js socket applications, get authenticated, validated, and immediately pushed into Kafka topics for processing. The margin for error was essentially zero.

## The Security Challenge: Building Bulletproof Encryption

Working with financial services clients meant that security couldn't be an afterthought. The transactional flow required a sophisticated two-step encryption process that I had to master completely. Every user device would generate unique RSA key pairs through our SDK, sending the public keys to our backend for storage in Aerospike.

When sending notifications, we would generate a fresh AES key for each message, encrypt the notification payload with this AES key, then encrypt the AES key itself using the device's specific RSA public key. Both pieces would be sent together, allowing only that specific device to decrypt and display the notification. It was an elegant and secure approach.

The system also needed to track user consent at a granular level – both promotional and transactional notifications required explicit user permission. Our SDK would capture consent from users in the client app and send it to our backend, where it was stored at the user level in Aerospike for validation during notification processing.

## The Node.js Performance Wall

As the banking client's usage grew, we started hitting the fundamental limitations of our Node.js push sender. Despite our best optimization efforts – tuning Kafka configurations, optimizing consumer handlers, and addressing rebalancing issues – we could barely push through 5,000 events per minute. For an I/O intensive application, JavaScript's single-threaded nature was becoming a bottleneck we couldn't engineer around.

The Kafka issues were particularly frustrating. Consumer groups would constantly rebalance, disrupting our throughput and causing delivery delays. We tried everything – adjusting timeouts, tuning heartbeat intervals, optimizing our consumer code – but the problems persisted. Eventually, we discovered that the real issue was our Azure HDInsight Kafka setup. Migrating to a standalone Kafka cluster resolved the rebalancing issues, but the fundamental performance limitations remained.

## Building the Future: The Java Push Sender Revolution

Faced with these limitations, our team made a bold decision – we would rewrite the entire push sender from scratch in Java Spring Boot. This wasn't just about changing languages; it was about reimagining how a high-performance notification system should work.

I took on this challenge with enthusiasm, using AI tools like Windsurf not as a crutch, but as a collaboration partner. I would design the architecture, write the code, and then use AI to review and suggest improvements. Every suggestion was carefully evaluated, modified to match my coding style, and integrated only if it truly improved the solution.

The architecture I built was something I'm genuinely proud of. Using SOLID principles and carefully chosen design patterns, I created a system of abstractions and interfaces that could handle not just the banking client's specific requirements, but also the varied payload types from our main Marketing Automation flow used by all other clients. The code was designed for reusability, maintainability, and future extensibility.

When we finally deployed the Java push sender, the results were staggering. On the exact same hardware that struggled to handle 5,000 events per minute in Node.js, our Java application was processing 150,000 events per minute – a 30x performance improvement. We rolled it out across all regions and all clients, replacing years of accumulated technical debt with a single, unified solution.

## The Art of Performance Optimization

One of the most satisfying moments of my career came from what seemed like a trivial change. While performance testing our Android notification flow, I noticed we were hitting a throughput ceiling around 33,000 events per minute. Something was creating a bottleneck, but it wasn't obvious what.

Diving into the code, I found the culprit in our batching logic. Every time we added a payload to a batch, we were converting the entire JSON array to a string and calculating its byte length. For a batch of 50 items, this meant the first addition took microseconds, but by the 49th addition, we were spending nearly 3 milliseconds just calculating sizes.

The fix was embarrassingly simple – instead of recalculating the entire batch size each time, just add the new payload's size to a running total. One line of code changed, and our throughput improved dramatically. It was a perfect reminder that performance optimization is often about understanding exactly what your code is doing, not just making it more complex.

## Innovation in Notification Reliability

The pull notifications experiment from my internship days evolved into a comprehensive solution for notification reliability. Modern mobile operating systems are increasingly aggressive about limiting background processing, meaning traditional push notifications sometimes fail to reach users even when their devices are online.

I designed and implemented a sophisticated system to handle this challenge. Background workers on Android and BGAppRefreshTasks on iOS would periodically refresh device tokens and check for missed notifications. When the app couldn't run these background tasks, we would send silent push notifications to trigger the refresh process.

The backend component I built could scan our Aerospike database for tokens that hadn't been refreshed recently, identify users who might have missed notifications, and intelligently send silent pushes to wake up their apps. The system was capable of processing 230,000 events per minute while making complex decisions about user behavior patterns and notification delivery success rates.

## Problem-Solving & Issue Resolution

Not every challenge was about building new systems. A significant part of my role involved diagnosing and resolving critical issues that could impact client functionality. Here are a couple of examples:

**Android Compatibility Issue:** When a client upgraded their Google Ads Identifier library to version 18.2.0, Android 7 devices started crashing. The investigation revealed that the newer library was using Java 8 APIs like `java.time.Duration` that didn't exist on older Android versions. I provided solutions including core library desugaring and documented the process for future reference.

**Arabic Text Encoding Issue:** We encountered a problem where Arabic text was being displayed as gibberish to users. The issue stemmed from a change in the format that clients were sending Arabic text, and our decoding logic wasn't handling the new format properly. I fixed the decoding implementation to work robustly across different text formats, ensuring proper display of Arabic content.

These are just two issues I remember from the many bugs and technical challenges I've diagnosed and resolved throughout my time at the company.

## The Infrastructure Behind the Code

Throughout this journey, I was also learning the operational side of software development. I dockerized applications, managed Kubernetes deployments through Devtron, and maintained the complex web of services that kept everything running. Setting up monitoring with Prometheus and Grafana, optimizing Aerospike queries with User Defined Functions, and managing certificate rotations for FCM and APNS might not be glamorous work, but it's the foundation that allows the exciting features to actually function reliably.

## Security Hardening and Trust

Working with financial services clients meant that security couldn't be an afterthought. I implemented certificate pinning for iOS SDK API calls, designed secure token management systems, and ensured that every piece of sensitive data was handled with appropriate encryption and access controls. These weren't just technical requirements – they were about building systems that clients could trust with their most sensitive communications.

## Looking Forward: From Journey to Destination

As I reflect on this journey from intern to full-time engineer, what strikes me most is how each challenge built upon the previous ones. The debugging skills I learned during on-call rotations helped me optimize performance bottlenecks. The cross-platform SDK work prepared me for thinking about system architecture. The infrastructure improvements taught me to think beyond just writing code to understanding the complete operational picture.

I've gone from someone who needed tutorials to understand Spring Boot to someone who can design and implement systems that handle hundreds of thousands of events per minute. I've learned to balance the demands of high-performance systems with the reliability requirements of financial services. I've experienced the satisfaction of both finding critical bugs and building entirely new capabilities.

But perhaps most importantly, I've learned that great engineering isn't just about writing clever code – it's about understanding problems deeply, designing sustainable solutions, and building systems that other people can depend on. Every notification that reaches a user's device, every system that stays up during peak traffic, every bug that gets fixed before it impacts production – these are the real measures of success.

The journey continues, and I'm ready for whatever challenges come next.