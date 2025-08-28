<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); padding: 3rem 2rem; border-radius: 20px; margin-bottom: 2rem; color: white; text-align: center; position: relative; overflow: hidden;">
  <div style="position: absolute; top: -50px; right: -50px; width: 100px; height: 100px; background: rgba(255,255,255,0.1); border-radius: 50%;"></div>
  <div style="position: absolute; bottom: -30px; left: -30px; width: 60px; height: 60px; background: rgba(255,255,255,0.1); border-radius: 50%;"></div>
  
  <h1 style="color: white; margin: 0; font-size: 2.5rem; text-shadow: 2px 2px 4px rgba(0,0,0,0.3);">
    🚀 The Full-Time Evolution
  </h1>
  <p style="font-size: 1.3rem; margin: 1rem 0 0 0; color: rgba(255,255,255,0.9); font-style: italic;">
    July 2023 - Present • Sections 6-10 from the original journey
  </p>
</div>

<div style="position: relative; margin-left: 3rem;">
  <div style="position: absolute; left: -3rem; top: 0; bottom: 0; width: 4px; background: linear-gradient(to bottom, #9b59b6, #e67e22, #1abc9c, #34495e, #8e44ad); border-radius: 2px;"></div>

  <div style="background: linear-gradient(135deg, #e67e22 0%, #d35400 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #e67e22; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">6</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🏦 Transition to Full-Time: Entering the Banking Client Universe</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        When my internship ended and I transitioned to a full-time SDE role, I thought I understood what I was getting into. I was wrong. The banking client stack was a completely different beast – simpler in some ways, but carrying the weight of being one of our most critical clients. This was a bank's critical infrastructure, and there was no room for error.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The banking client's world revolved around two fundamental flows: promotional campaigns that arrived as batch files via SFTP, and real-time transactional notifications that came through socket connections. Each flow had its own personality, its own challenges, and its own requirements for reliability and security.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px;">
        <div style="text-align: center; margin-bottom: 1rem;">
          <div style="font-size: 2rem; margin-bottom: 0.5rem;">📁</div>
          <strong style="color: white; display: block;">Promotional Flow</strong>
        </div>
        <p style="color: rgba(255,255,255,0.9); font-size: 0.9rem; margin: 0;">
          The promotional flow felt like watching a well-orchestrated machine. Files would arrive on our SFTP server, get picked up by cron jobs, transferred to processing VMs where Flume applications would transform and validate the data before feeding it into Kafka. It was batch processing at scale, requiring careful attention to error handling and data integrity.
        </p>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px;">
        <div style="text-align: center; margin-bottom: 1rem;">
          <div style="font-size: 2rem; margin-bottom: 0.5rem;">⚡</div>
          <strong style="color: white; display: block;">Transactional Flow</strong>
        </div>
        <p style="color: rgba(255,255,255,0.9); font-size: 0.9rem; margin: 0;">
          The transactional flow was the complete opposite – real-time, high-stakes, and demanding instant responses. Notifications would arrive through our Node.js socket applications, get authenticated, validated, and immediately pushed into Kafka topics for processing. The margin for error was essentially zero.
        </p>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">🎯 Mission Critical:</strong> Banking infrastructure with zero tolerance for errors
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #1abc9c 0%, #16a085 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #1abc9c; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">7</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🔒 The Security Challenge: Building Bulletproof Encryption</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Working with financial services clients meant that security couldn't be an afterthought. The transactional flow required a sophisticated two-step encryption process that I had to master completely. Every user device would generate unique RSA key pairs through our SDK, sending the public keys to our backend for storage in Aerospike.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        When sending notifications, we would generate a fresh AES key for each message, encrypt the notification payload with this AES key, then encrypt the AES key itself using the device's specific RSA public key. Both pieces would be sent together, allowing only that specific device to decrypt and display the notification. It was an elegant and secure approach.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The system also needed to track user consent at a granular level – both promotional and transactional notifications required explicit user permission. Our SDK would capture consent from users in the client app and send it to our backend, where it was stored at the user level in Aerospike for validation during notification processing.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🔑</div>
        <strong style="color: white;">RSA Encryption</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🛡️</div>
        <strong style="color: white;">AES Security</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">✅</div>
        <strong style="color: white;">User Consent</strong>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">🔐 Security Architecture:</strong> Two-step encryption with device-specific RSA keys and fresh AES keys for each message
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #34495e 0%, #2c3e50 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #34495e; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">8</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🚧 The Node.js Performance Wall</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        As the banking client's usage grew, we started hitting the fundamental limitations of our Node.js push sender. Despite our best optimization efforts – tuning Kafka configurations, optimizing consumer handlers, and addressing rebalancing issues – we could barely push through 5,000 events per minute. For an I/O intensive application, JavaScript's single-threaded nature was becoming a bottleneck we couldn't engineer around.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The Kafka issues were particularly frustrating. Consumer groups would constantly rebalance, disrupting our throughput and causing delivery delays. We tried everything – adjusting timeouts, tuning heartbeat intervals, optimizing our consumer code – but the problems persisted. Eventually, we discovered that the real issue was our Azure HDInsight Kafka setup. Migrating to a standalone Kafka cluster resolved the rebalancing issues, but the fundamental performance limitations remained.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📊</div>
        <strong style="color: white; display: block;">Throughput Limit</strong>
        <span style="color: rgba(255,255,255,0.8); font-size: 0.9rem;">5,000 events/min</span>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">⚠️</div>
        <strong style="color: white; display: block;">Bottleneck</strong>
        <span style="color: rgba(255,255,255,0.8); font-size: 0.9rem;">Single-threaded JS</span>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">🔍 Root Cause:</strong> JavaScript's single-threaded nature became an insurmountable bottleneck for high-throughput processing
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #8e44ad 0%, #9b59b6 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #8e44ad; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">9</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🚀 Building the Future: The Java Push Sender Revolution</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Faced with these limitations, our team made a bold decision – we would rewrite the entire push sender from scratch in Java Spring Boot. This wasn't just about changing languages; it was about reimagining how a high-performance notification system should work.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        I took on this challenge with enthusiasm, using AI tools like Windsurf not as a crutch, but as a collaboration partner. I would design the architecture, write the code, and then use AI to review and suggest improvements. Every suggestion was carefully evaluated, modified to match my coding style, and integrated only if it truly improved the solution.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The architecture I built was something I'm genuinely proud of. Using SOLID principles and carefully chosen design patterns, I created a system of abstractions and interfaces that could handle not just the banking client's specific requirements, but also the varied payload types from our main Marketing Automation flow used by all other clients. The code was designed for reusability, maintainability, and future extensibility.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📈</div>
        <strong style="color: white; display: block;">Before</strong>
        <span style="color: rgba(255,255,255,0.8); font-size: 0.9rem;">5,000 events/min</span>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🚀</div>
        <strong style="color: white; display: block;">After</strong>
        <span style="color: rgba(255,255,255,0.8); font-size: 0.9rem;">150,000 events/min</span>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">🎯 Revolutionary Result:</strong> 30x performance improvement on the same hardware - replaced years of technical debt with a unified solution
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-top: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        When we finally deployed the Java push sender, the results were staggering. On the exact same hardware that struggled to handle 5,000 events per minute in Node.js, our Java application was processing 150,000 events per minute – a 30x performance improvement. We rolled it out across all regions and all clients, replacing years of accumulated technical debt with a single, unified solution.
      </p>
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #f1c40f 0%, #f39c12 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #f1c40f; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">10</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🎨 The Art of Performance Optimization</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        One of the most satisfying moments of my career came from what seemed like a trivial change. While performance testing our Android notification flow, I noticed we were hitting a throughput ceiling around 33,000 events per minute. Something was creating a bottleneck, but it wasn't obvious what.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Diving into the code, I found the culprit in our batching logic. Every time we added a payload to a batch, we were converting the entire JSON array to a string and calculating its byte length. For a batch of 50 items, this meant the first addition took microseconds, but by the 49th addition, we were spending nearly 3 milliseconds just calculating sizes.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The fix was embarrassingly simple – instead of recalculating the entire batch size each time, just add the new payload's size to a running total. One line of code changed, and our throughput improved dramatically. It was a perfect reminder that performance optimization is often about understanding exactly what your code is doing, not just making it more complex.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🔍</div>
        <strong style="color: white; display: block;">Problem</strong>
        <span style="color: rgba(255,255,255,0.8); font-size: 0.9rem;">Inefficient batching</span>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">⚡</div>
        <strong style="color: white; display: block;">Solution</strong>
        <span style="color: rgba(255,255,255,0.8); font-size: 0.9rem;">One line fix</span>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">💡 Key Insight:</strong> Performance optimization is about understanding exactly what your code is doing, not making it more complex
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #16a085 0%, #1abc9c 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #16a085; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">11</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">💡 Innovation in Notification Reliability</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The pull notifications experiment from my internship days evolved into a comprehensive solution for notification reliability. Modern mobile operating systems are increasingly aggressive about limiting background processing, meaning traditional push notifications sometimes fail to reach users even when their devices are online.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        I designed and implemented a sophisticated system to handle this challenge. Background workers on Android and BGAppRefreshTasks on iOS would periodically refresh device tokens and check for missed notifications. When the app couldn't run these background tasks, we would send silent push notifications to trigger the refresh process.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        The backend component I built could scan our Aerospike database for tokens that hadn't been refreshed recently, identify users who might have missed notifications, and intelligently send silent pushes to wake up their apps. The system was capable of processing 230,000 events per minute while making complex decisions about user behavior patterns and notification delivery success rates.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📱</div>
        <strong style="color: white;">Android Workers</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🍎</div>
        <strong style="color: white;">iOS BGAppRefresh</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🔔</div>
        <strong style="color: white;">Silent Push</strong>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">⚡ Performance:</strong> 230,000 events per minute with intelligent user behavior pattern analysis
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #c0392b 0%, #e74c3c 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #c0392b; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">12</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🔧 Problem-Solving & Issue Resolution</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Not every challenge was about building new systems. A significant part of my role involved diagnosing and resolving critical issues that could impact client functionality. Here are a couple of examples:
      </p>
    </div>

    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px;">
        <div style="text-align: center; margin-bottom: 1rem;">
          <div style="font-size: 2rem; margin-bottom: 0.5rem;">📱</div>
          <strong style="color: white; display: block;">Android Compatibility Issue</strong>
        </div>
        <p style="color: rgba(255,255,255,0.9); font-size: 0.9rem; margin: 0;">
          When a client upgraded their Google Ads Identifier library to version 18.2.0, Android 7 devices started crashing. The investigation revealed that the newer library was using Java 8 APIs like `java.time.Duration` that didn't exist on older Android versions. I provided solutions including core library desugaring and documented the process for future reference.
        </p>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px;">
        <div style="text-align: center; margin-bottom: 1rem;">
          <div style="font-size: 2rem; margin-bottom: 0.5rem;">🌐</div>
          <strong style="color: white; display: block;">Arabic Text Encoding Issue</strong>
        </div>
        <p style="color: rgba(255,255,255,0.9); font-size: 0.9rem; margin: 0;">
          We encountered a problem where Arabic text was being displayed as gibberish to users. The issue stemmed from a change in the format that clients were sending Arabic text, and our decoding logic wasn't handling the new format properly. I fixed the decoding implementation to work robustly across different text formats, ensuring proper display of Arabic content.
        </p>
      </div>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; border-left: 4px solid rgba(255,255,255,0.5);">
      <strong style="color: white;">🎯 Impact:</strong> These are just two issues I remember from the many bugs and technical challenges I've diagnosed and resolved throughout my time at the company.
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #27ae60 0%, #2ecc71 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #27ae60; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">13</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🏗️ The Infrastructure Behind the Code</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Throughout this journey, I was also learning the operational side of software development. I dockerized applications, managed Kubernetes deployments through Devtron, and maintained the complex web of services that kept everything running. Setting up monitoring with Prometheus and Grafana, optimizing Aerospike queries with User Defined Functions, and managing certificate rotations for FCM and APNS might not be glamorous work, but it's the foundation that allows the exciting features to actually function reliably.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🐳</div>
        <strong style="color: white;">Docker</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">☸️</div>
        <strong style="color: white;">Kubernetes</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📊</div>
        <strong style="color: white;">Prometheus</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📈</div>
        <strong style="color: white;">Grafana</strong>
      </div>
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #d35400 0%, #e67e22 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #d35400; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">14</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🛡️ Security Hardening and Trust</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        Working with financial services clients meant that security couldn't be an afterthought. I implemented certificate pinning for iOS SDK API calls, designed secure token management systems, and ensured that every piece of sensitive data was handled with appropriate encryption and access controls. These weren't just technical requirements – they were about building systems that clients could trust with their most sensitive communications.
      </p>
    </div>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin: 1.5rem 0;">
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">📌</div>
        <strong style="color: white;">Certificate Pinning</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🔐</div>
        <strong style="color: white;">Token Management</strong>
      </div>
      <div style="background: rgba(255,255,255,0.15); padding: 1rem; border-radius: 8px; text-align: center;">
        <div style="font-size: 2rem; margin-bottom: 0.5rem;">🛡️</div>
        <strong style="color: white;">Access Controls</strong>
      </div>
    </div>
  </div>

  <div style="background: linear-gradient(135deg, #8e44ad 0%, #9b59b6 100%); padding: 2rem; border-radius: 12px; margin-bottom: 3rem; color: white; position: relative;">
    <div style="position: absolute; left: -3rem; top: 2rem; width: 2rem; height: 2rem; background: #8e44ad; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="color: white; font-weight: bold;">15</span>
    </div>
    <h2 style="color: white; margin-top: 0; font-size: 1.8rem;">🌟 Looking Forward: From Journey to Destination</h2>
    
    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        As I reflect on this journey from intern to full-time engineer, what strikes me most is how each challenge built upon the previous ones. The debugging skills I learned during on-call rotations helped me optimize performance bottlenecks. The cross-platform SDK work prepared me for thinking about system architecture. The infrastructure improvements taught me to think beyond just writing code to understanding the complete operational picture.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        I've gone from someone who needed tutorials to understand Spring Boot to someone who can design and implement systems that handle hundreds of thousands of events per minute. I've learned to balance the demands of high-performance systems with the reliability requirements of financial services. I've experienced the satisfaction of both finding critical bugs and building entirely new capabilities.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px; margin-bottom: 1.5rem;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0;">
        But perhaps most importantly, I've learned that great engineering isn't just about writing clever code – it's about understanding problems deeply, designing sustainable solutions, and building systems that other people can depend on. Every notification that reaches a user's device, every system that stays up during peak traffic, every bug that gets fixed before it impacts production – these are the real measures of success.
      </p>
    </div>

    <div style="background: rgba(255,255,255,0.15); padding: 1.5rem; border-radius: 8px; text-align: center;">
      <p style="color: rgba(255,255,255,0.95); line-height: 1.6; margin: 0; font-size: 1.1rem; font-weight: bold;">
        The journey continues, and I'm ready for whatever challenges come next.
      </p>
    </div>
  </div>

</div>

## 🎯 Full-Time Journey Impact

<div style="background: linear-gradient(135deg, #34495e, #2c3e50); padding: 2rem; border-radius: 12px; color: white; margin: 2rem 0;">
  <h3 style="color: white; margin-top: 0;">Transforming from Intern to System Architect</h3>
  <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem; margin-top: 1.5rem;">
    <div>
      <h4 style="color: #e67e22; margin-bottom: 0.5rem;">🏛️ Enterprise Ready</h4>
      <p style="margin: 0; opacity: 0.9; line-height: 1.5;">Successfully transitioned to working with banking clients, implementing enterprise-grade security and compliance requirements.</p>
    </div>
    <div>
      <h4 style="color: #1abc9c; margin-bottom: 0.5rem;">🔒 Security Expert</h4>
      <p style="margin: 0; opacity: 0.9; line-height: 1.5;">Designed and implemented end-to-end encryption systems that meet banking industry security standards.</p>
    </div>
    <div>
      <h4 style="color: #8e44ad; margin-bottom: 0.5rem;">🏗️ System Architect</h4>
      <p style="margin: 0; opacity: 0.9; line-height: 1.5;">Led the complete architectural overhaul from Node.js to Java Spring Boot, achieving 30x performance improvement.</p>
    </div>
  </div>
</div>

---

<div style="text-align: center; margin: 3rem 0; padding: 2rem; background: #f8f9fa; border-radius: 12px;">
  <h3 style="color: #2c3e50; margin-bottom: 1rem;">Explore More of the Journey</h3>
  <p style="color: #7f8c8d; margin-bottom: 2rem;">Discover the technical innovations and problem-solving achievements</p>
  
  <div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap;">
    <a href="lemnisk_internship.html" style="background: #3498db; color: white; padding: 1rem 2rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
      ← Internship Story
    </a>
    <a href="lemnisk_overview.html" style="background: #95a5a6; color: white; padding: 1rem 2rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
      Back to Overview
    </a>
  </div>
</div>
